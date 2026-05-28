# AI GTM Research & Outreach System
### Replace 12.5 hours of manual company research with a 30-second automated pipeline

Built with **n8n · Groq AI (Llama 3.1) · JavaScript · Google Sheets**

---

## What It Does

A sales rep spending 15 minutes per company × 50 companies = **12.5 hours of manual work per week.**

This system takes any company name as input and outputs structured research + a personalized cold email angle in **under 6 seconds** — with zero manual effort.

It doesn't just research companies. It finds **trigger events** — real business signals like funding rounds, hiring surges, and product launches — and uses them to generate outreach angles that feel timely and relevant, not templated.

---

## Live Output

👉 [Google Sheets — Real data](https://docs.google.com/spreadsheets/d/1FiWJZF2R1YYaoZI1dG0xsmb2dcnaYJ6QHxkqvm-rNA4/edit?usp=sharing)

---

## Results

| Metric | Before | After |
|--------|--------|-------|
| Time per company | 15 minutes | ~6 seconds |
| Time for 50 companies | 12.5 hours | Under 5 minutes |
| Manual effort | High | Zero |
| Outreach quality | Generic | Trigger-based, timely |

---

## What Gets Generated Per Company

For every company submitted, the system auto-generates 6 fields:

- **Company** — name
- **What they do** — one specific sentence, no fluff
- **Target customer** — who actually buys from them
- **Core pain point** — the #1 problem their buyers feel daily
- **Trigger event** — recent funding, hiring surge, or product launch that makes NOW the right time to reach out
- **Outreach angle** — one bold sentence referencing the trigger event and pain point

**Example output for Stripe:**
- Trigger event: *$600M funding round for online payments expansion into Southeast Asia and Latin America*
- Outreach angle: *With your e-commerce growth accelerating in Southeast Asia and Latin America, now is the perfect time to reassess your payment processing fees to ensure you're not hemorrhaging money on unnecessary charges.*

---

## How It Works

```
Webhook trigger → Groq AI research → JSON parser → Google Sheets
```

1. Submit a company name via webhook (from any form, tool, or system)
2. Groq AI researches the company and returns structured JSON
3. JavaScript parses and validates the output
4. Data is automatically appended to Google Sheets

Fully trigger-based. No manual execution required.

---

## Setup

### Prerequisites
- [n8n](https://n8n.io/) (self-hosted or cloud)
- [Groq API key](https://console.groq.com/) (free tier works)
- Google Sheets account

### Steps

1. Clone this repo
2. Import `workflow/gtm_research_agent.json` into your n8n instance
3. Add your Groq API key to the n8n credential store
4. Connect your Google Sheets account in n8n
5. Update the Sheets node with your own spreadsheet ID
6. Activate the workflow and hit the webhook URL with `{ "company": "Stripe" }`

---

## Repo Structure

```
ai-gtm-research-agent/
├── workflow/
│   └── gtm_research_agent.json     # n8n workflow export
├── templates/
│   └── cold_email_prompt.txt       # Groq prompt template
├── sheets/
│   └── schema.md                   # Column names + data structure
└── assets/
    └── workflow-screenshot.png     # n8n canvas screenshot
```

---

## Roadmap

- [ ] Email sending integration (Instantly.ai / HubSpot)
- [ ] Batch processing (CSV of 100+ companies)
- [ ] Lead scoring layer (rank by trigger event strength)
- [ ] Slack notifications for high-score leads

---

## Built By

**Vinayak Gavimath** · May 2026  
BCA First Year · Manipal University Jaipur  
[LinkedIn](https://linkedin.com/in/vinayak-g-) · [Portfolio](https://vinayakgavimath.github.io/vinayak-g)
