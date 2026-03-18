# AymenOu SQL Studio Demo Script (5 Minutes)

## Goal
Show that users can ask business questions in plain English, get SQL automatically, and export results quickly.

## Demo Setup (Before Speaking)
1. Activate virtual environment.
2. Ensure Ollama is running and model is available: `llama3.2`.
3. Start app: `python web_app_v2.py`.
4. Open `http://localhost:5000`.

## Speaking Script

### 1. Problem (30s)
"Most business users do not write SQL. This tool lets them ask questions in natural language and still query real databases safely."

### 2. Product Intro (30s)
"This is AymenOu SQL Studio. It supports local SQLite for quick use and PostgreSQL for cloud data. It can generate SQL, run it, and display results immediately."

### 3. Live Query 1 (60s)
1. Click an example in Employees.
2. Show generated SQL block.
3. Highlight automatic table results.

Say:
"The app translates question to SQL and executes it directly. The SQL is visible, so analysts can verify it."

### 4. Live Query 2 (60s)
1. Switch category to Sales.
2. Run "Top 3 salespeople by total amount".
3. Show result table and row count.

Say:
"We can move between business domains and keep the same workflow: ask, generate SQL, validate, export."

### 5. Export Features (45s)
1. Click `CSV` to export table only.
2. Click `SQL+Result` to export full report (question + SQL + result CSV block).

Say:
"Export works in two modes: data-only CSV, or complete report for audit and sharing."

### 6. Safety and Control (45s)
Say:
"The project includes read-only SQL validation, blocked destructive keywords, and max row limits to keep responses safe and fast."

### 7. Closing (30s)
"In short: this project removes the SQL barrier, keeps technical transparency, and speeds up decision-making for non-technical users."

## Backup Plan (If Demo Fails)
1. Show screenshots from `screenshots/`.
2. Open generated SQL in chat history.
3. Explain architecture quickly from `README.md`.

## Quick QA Answers
- "Is it offline?" -> Yes, with Ollama backend.
- "Can it use cloud models?" -> Yes, OpenAI/Anthropic via env vars.
- "Can we connect external DB?" -> Yes, PostgreSQL in web app and SQL Server in `agent.py`.
- "How is it safer than direct LLM SQL?" -> Read-only checks + row limits + visible SQL for verification.
