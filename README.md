# AI-Powered Instagram Cold Outreach Workflow

This workflow automates the entire cold outreach funnel for coaches. It goes beyond simple templates by using AI to research each lead individually and draft personalized messages that resonate with their specific fitness goals and interests.

## 🚀 Features

- **Automated Scraping:** Uses the **Apify Instagram Email Scraper** to find targeted leads based on custom keywords (e.g., bodybuilding, fitness, strength training).
- **Deep Lead Research:** Integrates **Tavily Search** to find recent information about each lead based on their Instagram bio and title, providing context for the AI.
- **AI Copywriting:** Employs **GPT-4o (via OpenRouter)** and **LangChain Agents** to write personalized, casual, and non-pushy emails following a specific proven structure.
- **Email Rotation:** Features a **Switch node** that rotates outgoing emails between three different Gmail accounts to manage daily sending limits and protect account reputation.
- **Data Logging:** Appends all lead data, including the AI-generated subject and body, to a **Google Sheet** for tracking and CRM purposes.
- **Smart Delays:** Includes a 150-second **Wait node** between emails to ensure human-like delivery patterns.

## 🛠️ Prerequisites

To use this workflow, you will need:
- An **n8n** instance.
- **Apify API Key** (for Instagram scraping).
- **Tavily API Key** (for lead research).
- **OpenRouter API Key** (for access to GPT-4o).
- **Google Sheets OAuth2** and **Gmail OAuth2** credentials for multiple accounts.

## ⚙️ How It Works

1.  **Trigger:** Initiated via a **Webhook** receiving `instagramKeywords`.
2.  **Scrape:** Apify extracts up to 150 leads matching the keywords.
3.  **Research:** For each lead, Tavily searches for recent online activity to gather "talking points".
4.  **Draft:** The AI agent generates a short, 5-line email in a "friendly brother" tone, including a specific Calendly link.
5.  **Rotate & Send:** The workflow randomly selects one of three Gmail accounts and sends the personalized message.
6.  **Log:** The lead's details and the sent message are saved to the "Outreach data instagram ismail" spreadsheet.

## 📦 Installation

1. Download the `automated cold outreach instagram.json` file.
2. Open your n8n dashboard and click on **Import from File**.
3. Configure your API credentials for **Apify, Tavily, OpenRouter, Google Sheets,** and **Gmail**.
4. Update the Calendly link and the Gmail addresses in the **Write email** and **Switch** nodes respectively to match your own details.
