### **Flow Description**

1. **Input Parameters**:
    - `query`: The question or query string for retrieving relevant project information.
    - `additional_info`: Any additional context to augment the query.
    - `context_config`: Configuration object specifying how the context is retrieved.
    - `kendra_filters`: Filters to apply while querying the knowledge base (Kendra).
    - `num_references`: Maximum number of references to retrieve (default: 10).
    - `kwargs`: Other optional parameters, such as `activity_name`, `task`, and `task_number`.

---

2. **Step 1: Retrieve Contexts from Knowledge Base**
    - **Call**: `rag_handler`
        - Queries the knowledge base with the provided `query`, `context_config`, and filters.
        - **Parameters**:
            - `query`: The main query string.
            - `context_config`: Configuration details for the RAG pipeline.
            - `num_references`: Number of documents to retrieve.
            - `kendra_attribute_filters`: Filters for narrowing down results.
        - **Output**: `kb_contexts`, containing responses with relevant documents.

---

3. **Step 2: Transform Documents**
    - **For Loop**:
        - Iterates over `kb_contexts.responses`.
        - **Transform**: Uses `transform_document_data` to process each document.
        - **Generate Context ID**: Assigns a unique ID (`context_id`) to each transformed document.
        - **Clean Context**: Strips unnecessary data using `clean_context`.
        - **Store**: Updates `source_documents` and a `context` dictionary.

---

4. **Step 3: Prepare System Prompt**
    - **Template**: Formats `SWMS_PROJECT_INFO_PER_TASK_SYSTEM_PROMPT_TEMPLATE` with:
        - `activity_name`: Activity related to the task (from `kwargs`).
        - `task`: Task description (from `kwargs`).
        - `additional_info`: Additional information.
        - `context`: Processed document contexts.
    - **Messages**:
        - System message: Sets the context and task description.
        - User message: Contains the original query.

---

5. **Step 4: Generate Response from LLM**
    - **Call**: `azure_openai_helper.generate_response`
        - Sends formatted messages to the LLM (`gpt-4o`).
        - Configured with:
            - `prompt`: The formatted system and user messages.
            - `model_id`: Specifies the LLM to use.
            - `use_instructor`: Enables guided generation.
            - `pydantic_model_type`: Defines the expected response format (`risk_controls`).
    - **Output**: Extracts `risks_and_controls` from the LLM response.

---

6. **Step 5: Parse LLM Response**
    - **For Loop**:
        - Iterates over `risks_and_controls`.
        - **Sort Controls**: Sorts controls for each risk by citation order (`sort_by_citation`).
        - **Tasks**:
            - Adds the current task if it's the first.
            - Adds an empty string for subsequent iterations.
        - **Risks**: Appends the risk description.
        - **Controls**: Formats controls with bullet points.

---

7. **Step 6: Remove Unused Citations**
    - **Call**: `remove_unused_citations`
        - Filters and removes unused citations from the response.

---

8. **Step 7: Update Citations with Section Number**
    - **Call**: `update_citations_with_section_number`
        - Adds a unique section number to citations based on `task_number`.

---

9. **Final Step: Return Consolidated Response**
    - Constructs `task_response` with:
        - `tasks`: The list of tasks.
        - `risks`: Associated risks.
        - `controls`: Mitigation controls.
        - `source_documents`: References used.
    - Returns the final structured `task_response`.