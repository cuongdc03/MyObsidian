Request:
```
{

"activity_name": "Transporting and unloading construction materials using flatbed trucks and forklifts at an active site",

"brief_description": "This activity emphasizes the secure transportation and unloading of materials utilizing flatbed trucks and forklifts to ensure efficiency and safety in a dynamic construction environment.",

"project_name": "Downtown Highrise Project",

  

"question":"Measure me about any dangerous if i do this project"

}
```
Response:
```
{

"chat_context_uid": "8b936eb0-755e-4b96-a97d-6172151b49cd",

"form_id": "1cd8e262-6987-4a2b-b4b9-7e326207182e",

"session_id": "b8115755-735d-4540-b149-217348844885",

"sender": "bot",

"message": "To better understand the potential dangers and generate a comprehensive Safe Work Method Statement (SWMS) for your project, could you please confirm if any of the following High-Risk Construction Work (HRCW) activities are applicable to your task of transporting and unloading materials using flatbed trucks and forklifts?\n\n- Work that involves a risk of a person falling more than two metres\n- Work on or near energised electrical installations or services\n- Work in areas in which there is movement of powered mobile plant\n- Work on, in or adjacent to a road, railway, shipping lane or other traffic corridor in use by traffic other than pedestrians\n\nAre any of these HRCW activities relevant to your project?",

"type": "response",

"documents": [],

"ofsc_compliant_document": null

}
```
### Flow of Clarifying Questions for SWMS Chat:

### **1. Receive the Activity Data**

- **Input**: The system receives details such as `activity_name`, `brief_description`, `question`, and project-specific information.

### **2. Generate the System Prompt**

- **Action**: The system generates a prompt with activity details and a brief description.
- **Output**: A structured template asking focused clarifying questions, starting with High-Risk Construction Work (HRCW):
    - "This activity involves transporting and unloading construction materials using flatbed trucks and forklifts. Can you confirm if any of the following High-Risk Construction Work activities apply?"
    - - Work that involves a risk of a person falling more than two metres
    - - Work on or near energised electrical installations or services
    - - Work in areas with movement of powered mobile plant
    - - Work on or near traffic corridors used by vehicles other than pedestrians

### **3. Fetch Chat History (if any)**

- **Action**: Check the session history from Redis or database.
- **Output**: If no history exists, initialize an empty list. If previous conversations exist, retrieve them to generate follow-up questions.

### **4. Ask About High-Risk Construction Work (HRCW)**

- **Action**: Generate questions based on the HRCW activities related to the activity description.
- **Output**: Example question:
    - "Are any of the following High-Risk Construction Work activities applicable to your project?"
    - - Work that involves a risk of a person falling more than two metres
    - - Work on or near energised electrical installations or services