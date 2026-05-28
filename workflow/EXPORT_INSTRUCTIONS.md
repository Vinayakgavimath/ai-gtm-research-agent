# Workflow Export

Place your exported n8n workflow JSON file here.

## How to Export

1. Open your workflow in n8n
2. Click the three-dot menu (top right of the canvas)
3. Select **Download**
4. Save the file as `gtm_research_agent.json` in this folder

## Before You Commit

Open the JSON file and search for any hardcoded values. Replace them with placeholders:

| Find | Replace With |
|------|-------------|
| Your actual Groq API key | `YOUR_GROQ_API_KEY` |
| Your Google Sheets spreadsheet ID | `YOUR_SHEETS_SPREADSHEET_ID` |
| Any personal email or account info | `YOUR_EMAIL` |

n8n credential objects are usually stored separately and won't appear in the workflow JSON — but double-check before pushing.
