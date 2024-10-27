# Meeting_minutes_automation
Meeting Minutes Automation using Power Automate  This Power Automate flow automates the generation and distribution of meeting minutes from user-submitted transcripts. The automation takes a transcript file created in SharePoint, processes it using Azure OpenAI, and sends a summarized version of the meeting minutes back to the user via email.

```mermaid
flowchart TD
    A[Start: User creates a file in SharePoint where all meeting transcripts are uploaded] --> B[Get file contents: extract the contents of the file that is uploaded]
    B --> C[HTTP: Provide authentication to a model by providing its URL, API key, and prompts in the body.Here, I have used GPT-4o-mini from Azure OpenAI studio]
    C --> D[Parse JSON: processes the response from the HTTP request, extracting structured data which allows subsequent action to utilize the generated meeting minutes effectively]
    D --> E[A temporary file is created in OneDrive to store the generated meeting minutes that I usually not in PDF format. This method is implemented for a safer file format conversion]
    E --> F[The converted file is later stored in a different destination folder in Sharepoint and finally deleted in OneDrive]
    F --> G[An email is sent to the person who uploaded the file in SharePoint while maintaining its copy in SharepPoint]
    G --> H[End]
