# PPE
- Query Creation: Generate Kendra query for PPE requirements.
- Kendra Search: Retrieve relevant documents and transform them into source documents.
- Prompt Creation: Use context and additional info to format LLM prompt.
- LLM Response: Generate PPE requirements (mandatory & task-specific).
- Post-process: Clean citations, adjust formatting, and structure the response.
- Return Final Response: The final response includes information depends on PPE/Permit/Plant Equipment
# Permit
- Query Creation: Generate Kendra query for PPE requirements.
- Kendra Search: Retrieve relevant documents and transform them into source documents.
- Prompt Creation: Use context and additional info to format LLM prompt.
- LLM Response: Generate PPE requirements (mandatory & task-specific).
- Post-process: Clean citations, adjust formatting, and structure the response.
- Return Final Response: The final response includes information depends on PPE/Permit/Plant Equipment
# Plant Equipment Mantenance
- Query Creation: Generate Kendra query for PPE requirements.
- Kendra Search: Retrieve relevant documents and transform them into source documents.
- Prompt Creation: Use context and additional info to format LLM prompt.
- LLM Response: Generate PPE requirements (mandatory & task-specific).
- Post-process: Clean citations, adjust formatting, and structure the response.
- Return Final Response: The final response includes information depends on PPE/Permit/Plant Equipment
![[Screenshot 2025-01-14 at 09.24.00.png]]
# Project Information
- Retrieve Context: It first fetches project context from Kendra based on the project and activity names. 
- Task Generation: A prompt is created using the context, and the AI model generates a list of tasks.
- Risk and Control Identification: For each task, the function queries Kendra again for related risks and controls, processing them concurrently. 
- Post-Processing: It organizes the tasks, risks, and controls in logical order, ensuring citations are consistent and relevant. 
- Return Final Response: The final response includes tasks, risks, controls, and source documents, formatted and ready for use.
![[Pasted image 20250114092501.png]]
# Pros/Cons
## Pros
Centralized Context Retrieval: Fetching project context from Kendra first allows the solution to use a comprehensive data set for task generation, ensuring that the AI model has the most up-to-date and relevant context.

Parallel Processing: The concurrent querying of risks and controls for each task helps to save time, improving efficiency in identifying related risks and controls without blocking operations.
## Cons
- Repeated Kendra Queries: Querying Kendra multiple times (once for the project context and again for risks/controls) may lead to slower performance, especially if there are a large number of tasks. This redundancy could increase API usage costs and response time.
- Complexity of Concurrent Processing: Managing multiple concurrent queries for risks and controls can introduce complexity in error handling, especially if one of the queries fails or returns incomplete data.
- Potential Overhead in Post-Processing: While post-processing ensures organization and citation consistency, it could add additional computational overhead, especially with a large number of tasks or documents.
## Improvement Way
- Decrease MAX_JOB_SEARCH: 10 -> 5  (Time reduced 14-17s -> 10-13s)
- 
# Request Indian Team
Test cases for AI Module: SWMS fill-template, SWMS Chat, Chat API Kindly inform us promptly of any changes to the API key.

## Benchmark
https://docs.google.com/spreadsheets/d/1ri-JD6WZU0oWuwEa1Ogp5EEVXzW6HZqPRetErjhGVFk/edit?gid=1733296033#gid=1733296033
