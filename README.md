# 🤖 24/7 AI Booking Agent

> Conversational AI that handles meeting scheduling entirely on its own — no human required.

## What It Does

When a prospect wants to book a meeting, this agent takes over completely:

1. Receives booking request via webhook
2. Gets current date and time automatically
3. AI understands natural language scheduling requests
4. Validates slot against business hours (Mon–Fri, 10am–5pm GMT+6)
5. Suggests alternatives if slot is unavailable
6. On confirmation — creates Google Calendar event with Meet link
7. Sends branded HTML confirmation email to the client
8. Returns booking details via webhook response

## Booking Schedule

| Parameter | Value |
|---|---|
| Available Days | Monday – Friday |
| Hours | 10:00 AM – 5:00 PM (GMT+6) |
| Slot Duration | 30 minutes |
| Weekends | Automatically rejected |

## Tech Stack

- **n8n** — workflow automation
- **Gemini / Ollama** — conversational AI
- **Google Calendar API** — event creation with Meet link
- **Gmail API** — HTML confirmation emails
- **Cloudflare Tunnel** — secure webhook exposure

## How to Use

1. Import `24_7 AI Booking Agent.json` into your n8n instance
2. Configure Google Calendar and Gmail OAuth2 credentials
3. Set your AI model credential (Gemini recommended)
4. Activate and expose webhook via Cloudflare Tunnel
5. Send POST requests to the webhook endpoint:
```json
{
  "name": "Client Name",
  "email": "client@email.com",
  "message": "I want to book a meeting tomorrow at 10am"
}
```

## Part of Spectre Flow Engine

This workflow is part of the [Spectre Flow](https://spectre-flow-website.vercel.app) AI infrastructure stack.

---
Built by [Ayanokouji](https://github.com/Darkus39) · Spectre Flow
