# Meeting_minutes_automation
Meeting Minutes Automation using Power Automate  This Power Automate flow automates the generation and distribution of meeting minutes from user-submitted transcripts. The automation takes a transcript file created in SharePoint, processes it using Azure OpenAI, and sends a summarized version of the meeting minutes back to the user via email.

```mermaid
flowchart TD
    A[Start: User submits meeting transcript via Microsoft Forms] --> B[Capture form response]
    B --> C[Store form response in variable]
    C --> D[Send transcript to Azure OpenAI for summarization]
    D --> E[Store generated meeting summary in a variable]
    E --> F[Generate meeting minutes document]
    F --> G[Email the document back to the user]
    G --> H[End]
