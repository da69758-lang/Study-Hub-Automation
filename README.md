# Study-Hub-Automation
A study Hub where you solve your doubts and can create the concepts or the questions
# Study Desk: an AI study assistant built with n8n

A web-based AI chat assistant powered by a local [n8n](https://n8n.io) workflow and Google Gemini, with a custom notebook-style chat page.

**How it works:** the browser page (`study-desk.html`) sends your message to an n8n Chat Trigger webhook. An AI Agent node answers using Gemini and remembers the conversation with Simple Memory. The answer comes back and is shown in the page.

```
study-desk.html  ->  n8n Chat Trigger  ->  AI Agent (Gemini + Simple Memory)  ->  reply
```

## Features

- Chat with memory, so follow-up questions work
- Markdown answers with copyable code blocks
- Suggestion chips, typing indicator, light and dark theme
- Runs fully on your own machine

## Setup

1. Install and start n8n locally (`npx n8n`), then open http://localhost:5678.
2. In n8n, choose **Import from File** and select `workflow.json`.
3. Open the **Google Gemini Chat Model** node and add your own free API key from [Google AI Studio](https://aistudio.google.com).
4. Open the **When chat message received** node:
   - Turn on **Make Chat Publicly Available**
   - Add **Allowed Origins (CORS)** and set it to `*`
5. Click **Publish**, then copy the **Chat URL** from the Chat Trigger node.
6. Open `study-desk.html` in your browser, click **Connection**, paste the Chat URL, and save.

## Built with

- n8n (Chat Trigger, AI Agent, Simple Memory)
- Google Gemini
- Plain HTML, CSS and JavaScript

## Ideas for next steps

- Add Wikipedia or web search tools to the agent
- Log questions to Google Sheets
- Replace Simple Memory with Postgres Chat Memory so history survives restarts
