## **Combine Multiple Prompts into a Single Request**

Original generate_answer(...): Check

```
def generate_answer(...):
    ...
    prompts = [
        {"prompt": prompt, "prompt_type": "json"},        # 1. main prompt
        {"prompt": redaction_prompt},                     # 2. redaction prompt
        {"prompt": search_explanation_prompt},            # 3. search explanation prompt
    ]

    results = run_parallel_invocations(*prompts)
    response = results[0]      # main system prompt output
    redacted_phrases = results[1].answer  # redaction output
    search_criteria = results[2].answer   # explanation output
    ...
```

we are making **3 separate requests** to the LLM in parallel. Each request can be large, incurring overhead and token usage.  
We can do something like this:  

````
def generate_answer(...):
    # 1) Construct a single system prompt that asks for:
    #    - The main answer,
    #    - The redaction info,
    #    - The search explanation
    combined_prompt = f"""
You are an AI assistant. Please do the following in ONE response:
1) **Answer** the user's question based on the <context> below.
2) **Extract** phrases that are personally identifying or sensitive (like phone numbers, full names, addresses).
3) **Explain** briefly in bullet points why these documents were chosen (matching tags, specific keywords, etc.).

<context>
{context}
</context>

User question:
{question}

Also reference these processed_docs for tags:
{json.dumps(processed_docs, indent=2)}

Output must be in JSON. 
Use this format exactly:

```json
{{
  "answer": "...",
  "redacted_phrases": ["...","..."],
  "search_explanation": "... (bullet points or short lines) ..."
}}
````

IMPORTANT: Do NOT add extra keys or text outside the JSON object. """   Check

```
# 2) We call the LLM once.
single_prompt_data = {
    "anthropic_version": "bedrock-2023-05-31",
    "max_tokens": 1024,  # or 512 if you can handle shorter completions
    "messages": [
        {
            "role": "user",
            "content": [{"type": "text", "text": combined_prompt}],
        }
    ],
    "temperature": 0.1,
}

# 3) Instead of run_parallel_invocations(...) with 3 prompts, do ONE invocation:
response = claude3_invoker_async_invoke(single_prompt_data)

# 4) We'll parse the single JSON.
#    Example: response.answer might be something like the JSON object as a string.
try:
    data = json.loads(response.answer)  # parse the JSON
    answer_text = data.get("answer", "")
    redacted_phrases = data.get("redacted_phrases", [])
    search_explanation = data.get("search_explanation", "")
except Exception as e:
    logger.error(f"Error parsing combined JSON response: {e}")
    # Fallback
    answer_text = response.answer
    redacted_phrases = []
    search_explanation = ""

# 5) Finish post-processing
# e.g. handle citations, references, etc.
# for example:
final_answer = do_post_processing_on_answer(
    answer_text, related_contexts.responses
)
# store or attach the search_explanation, redacted_phrases, etc.

return final_answer
```

````

### **New Helper**: `claude3_invoker_async_invoke(...)` Undone
 
```python
def claude3_invoker_async_invoke(prompt_data: dict) -> LLMResponse:
    """
    A synchronous wrapper that uses the existing 'claude3_invoker_async' 
    but with a single prompt.
    """
    async def _wrapper():
        async with claude3_invoker_async as invoker:
            return await invoker.invoke_model(prompt_data)

    return asyncio.run(_wrapper())
````

This approach **reduces** 3 calls -> 1 call

##   
Reduce & Summarize Context Before Sending to LLM Check but there is no changes in speed

Instead of passing every chunk from Kendra, do a small summarization or limit the top results. For instance, if you retrieve 10 documents from Kendra, you can do:  

```
MAX_FINAL_DOCS = 3

def rag_handler(...):
    ...
    # after sorting or merging
    final_responses = list(merged_results.values())

    # limit to top 3 docs
    final_responses = final_responses[:MAX_FINAL_DOCS]

    return RagHandlerResponse(responses=final_responses)
```

If you need more robust summarization, you can do:  Not yet

```
def quick_summarize(doc_text: str) -> str:
    # a small or local summarizer
    # or a quick LLM call. 
    # This is just pseudo-code:
    return doc_text[:500]  # naive: truncate to 500 chars
```

Then::  

```
for item in final_responses:
    content = item.context["Content"]
    item.context["Content"] = quick_summarize(content)
```

This drastically **reduces** tokens fed to the LLM.

##   
Avoid Listing All S3 Objects on Every Request

Original:  

```
s3_service = S3Service(
    bucket_name=context_config.s3_processed_bucket_name,
    region_name=aws_secret.AWS_REGION,
)
total_documents = len(s3_service.list_all_files())
```

If the bucket has thousands of documents, list_all_files() will be slow.  
we can improve by caching or storing document count  

```
def get_document_count_cached(context_name: str) -> int:
    # Example: Pull from Redis or your DB
    # Or store a simple dictionary if you rarely update
    # We'll do a placeholder:
    redis_count = redis_client.get(f"{context_name}_doc_count")
    return int(redis_count) if redis_count else 0

# Usage:
doc_count = get_document_count_cached(context_config.name)
additional_context = f"There are a total of {doc_count} docs..."
```

we can use redis to cache other thing that consumes the querying time

##   
Minimize String Replacements for Citations

The code does multiple answer.replace(f"[{old_id}]", placeholder) calls. Each pass can be O(N). For large strings, that’s costly.  
Improve: single-pass replacement  

```
def replace_citations(answer: str, id_map: Dict[str, str]) -> str:
    """
    id_map = { old_id: new_placeholder, ... }
    We do one pass with a regex or manually parse.
    """
    def replacer(match):
        full_str = match.group(0)  # e.g. "[22]"
        # strip brackets
        raw_id = full_str.strip("[]")
        return id_map.get(raw_id, full_str)

    # e.g. pattern to match `[digits]`
    pattern = re.compile(r"\[(\d+)\]")
    return pattern.sub(replacer, answer)

# Then usage:
id_map = {"22": "[1]", "23": "[2]"}  # old -> new
answer = replace_citations(answer, id_map)
```