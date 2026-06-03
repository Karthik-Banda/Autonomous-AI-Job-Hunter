🤖 Autonomous AI Job Hunter



An automated, LLM-powered job aggregation and evaluation pipeline built with n8n. This system autonomously scrapes job boards, evaluates roles against my specific technical skills using Google Gemini, generates tailored cover letters, and sends push notifications to Telegram.



🚀 Features



* Omni-Channel Aggregation: Utilizes SerpApi (Google Jobs) to pull real-time listings from LinkedIn, Indeed, Naukri, and Foundit simultaneously.
* Semantic LLM Evaluation: Integrates Google Gemini 1.5 Pro via LangChain to semantically compare job descriptions against my resume, scoring matches based on strict skill/experience constraints.
* Automated Asset Generation: Dynamically generates highly tailored cover letters and custom interview preparation questions for approved roles.
* Real-Time Telemetry: Sends formatted Markdown alerts to Telegram and logs all application data into Google Sheets for historical tracking.



🏗️ Architecture \& Tech Stack



* Orchestration: n8n (Workflow Automation)
* AI \& NLP: Google Gemini 1.5 Pro, LangChain Structured Output Parsers
* Data Ingestion: SerpApi (Google Jobs API)
* Notifications \& Logging: Telegram Bot API, Google Sheets API
* Logic: Custom JavaScript (Regex parsing, data mapping)



💡 How It Works



* Trigger: A CRON schedule triggers the workflow daily at 8:00 AM.
* Fetch: n8n sends a REST API request to fetch roles matching "Junior Full Stack Developer" or ".NET Developer".
* Batching: The raw JSON array is parsed using JavaScript and fed through a Loop node to prevent API rate limiting.
* Evaluation: Gemini analyzes the JD, outputs a boolean match score, and generates a cover letter.
* Routing: An algorithmic IF node filters out rejections. Approved jobs trigger the Telegram Webhook and log to Google Sheets.

