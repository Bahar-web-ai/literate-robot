# literate-robot
# AI-Powered Discord Feedback Router

An automated Discord agent that collects user feedback from an online form, analyzes it using an LLM, and intelligently routes each message to the correct Discord channel in real time.

This project combines **Discord API**, **n8n**, and **OpenAI** to create a fully functional AI-driven workflow for customer feedback management.

---

## 🚀 Features

- **Online Form Integration**  
  Users submit feedback through an external web form (Typeform, Tally, JotForm, etc.).

- **AI-Based Classification**  
  Feedback is analyzed using an LLM prompt and categorized into predefined groups (e.g., `success-story`, `urgent-issue`, `feature-request`).

- **Automated Discord Routing**  
  Each categorized message is automatically forwarded to the correct Discord channel.

- **n8n Workflow Automation**  
  The entire pipeline (webhook → AI → Discord) is orchestrated through n8n.

- **Real-time Processing**  
  Instant forwarding ensures the support and product teams receive feedback immediately.

---

## 🧠 How It Works

1. **User submits a feedback form**  
   → Form triggers a webhook.

2. **n8n receives the data**  
   → Extracts the feedback text.

3. **AI prompt classifies the message**  
   Example categories:
   - `success-story`
   - `urgent-issue`
   - `feature-request`
   - `general-feedback`

4. **Discord Bot posts to the right channel**  
   → Each category is routed to a dedicated group (e.g. customer success, support, engineering).

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| **n8n** | Workflow automation and orchestration |
| **OpenAI API** | LLM-based text classification |
| **Discord Bot API** | Posting messages to Discord channels |
| **Typeform / Tally / JotForm** | Online feedback collection |

---

## 📂 Project Structure

/n8n-workflow
workflow.json # Exported n8n workflow
/prompt
classifier_prompt.txt # The exact LLM classification prompt
/docs
architecture.png # (Optional) System diagram
README.md

---

## 📝 Example Prompt Used for Classification

```text
Here is a user feedback: "{{feedback}}".  
Please analyze it and classify it into one of the categories:  
1. "success-story" – positive feedback or user success  
2. "urgent-issue" – serious complaint or urgent problem  
3. "feature-request" – user asking for a new feature  
4. "general-feedback" – neutral comments or suggestions  

Return only the category name.

📡 Example Discord Output

Channel: #urgent-issue
Message:

🚨 New Urgent Issue Received
"The payment failed three times and I can’t complete my purchase."
From Online Feedback Form

🧪 Demo Use Case

This bot is ideal for:

SaaS customer feedback

Support ticket triage

Internal product feedback processing

Community moderation
