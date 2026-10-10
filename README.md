# B2B Lead Personalization and Email Automation
An automated workflow built in Google Workspace Studio. It leverages Gemini AI to process B2B lead data from Google Sheets, generates personalized sales outreach emails based on CRM notes, and creates ready-to-send drafts directly in Gmail.

## Workflow Architecture
The process operates on a sequential 7-step automation pipeline:

1. When a sheet changes: The workflow acts as a trigger, monitoring the designated Google Sheets CRM for any new rows or specific column updates.
2. Get sheet contents: The system retrieves the structured data from the triggered rows, including lead contact information and CRM notes.
3. Repeat for each item: A loop initializes to iterate through the list of retrieved leads, ensuring each record is processed individually.
4. Ask a Gem: A specialized AI agent processes the CRM notes and lead context to generate a highly personalized email body.
5. Ask Gemini: A secondary AI prompt analyzes the generated body and context to create a relevant email subject line.
6. Draft an email: The system connects to the Gmail API to create an email draft. It maps the recipient's address, the AI-generated subject, and the AI-generated body into the correct fields.
7. Update rows: The workflow writes back to the original Google Sheet, updating the lead's row with a status confirmation and the generated content for review.

## Tech Stack
* Google Workspace Studio
* Google Gemini LLM
* Google Sheets
* Gmail
