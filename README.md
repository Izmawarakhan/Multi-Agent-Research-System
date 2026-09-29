# 🔎 Multi-Agent Research System

An AI-powered **Multi-Agent Research System** built with **LangChain, Groq, Tavily, BeautifulSoup, and Streamlit**.

The system automates the research workflow by searching the web, scraping relevant sources, generating a structured research report, and reviewing the generated report using an AI critic.

## 🚀 Live Demo

🌐 **Streamlit App:**
https://multi-agent-research-system-0.streamlit.app/

## 📌 Features

* 🔍 **Web Search Agent** — searches the web for recent and relevant information using Tavily.
* 🌐 **Web Scraping Agent** — extracts useful information from selected webpages using BeautifulSoup.
* ✍️ **Research Writer** — generates a structured and professional research report.
* 🧐 **Research Critic** — reviews the generated report and provides feedback.
* 🤖 **Groq LLM** — powers the AI agents and research generation.
* 🔗 **LangChain Agents** — manages tool usage and agent workflows.
* 🎨 **Streamlit UI** — provides an interactive interface for running research.
* 📄 **Report Download** — allows users to download the generated research report.

## 🏗️ Architecture

```text
                    User
                      │
                      ▼
              ┌───────────────┐
              │   Streamlit   │
              │      UI       │
              └───────┬───────┘
                      │
                      ▼
             ┌──────────────────┐
             │   Search Agent   │
             │     LangChain    │
             └────────┬─────────┘
                      │
                      ▼
              ┌───────────────┐
              │     Tavily    │
              │   Web Search  │
              └───────┬───────┘
                      │
                      ▼
             ┌──────────────────┐
             │   Reader Agent   │
             │     LangChain    │
             └────────┬─────────┘
                      │
                      ▼
             ┌───────────────┐
             │ BeautifulSoup │
             │ Web Scraper   │
             └───────┬───────┘
                     │
                     ▼
             ┌──────────────────┐
             │  Writer Chain    │
             │   Research LLM   │
             └────────┬─────────┘
                      │
                      ▼
             ┌──────────────────┐
             │  Critic Chain    │
             │ AI Report Review  │
             └────────┬─────────┘
                      │
                      ▼
              Final Research Report
```

## 🧠 How It Works

### 1. Search Agent

The user enters a research topic.

The Search Agent uses the **Tavily Search API** to find relevant web sources and returns:

* Title
* URL
* Search snippet

### 2. Reader Agent

The Reader Agent receives the search results, identifies a relevant URL, and uses the **BeautifulSoup scraper** to extract useful webpage content.

### 3. Research Writer

The collected search results and scraped content are passed to the Writer Chain.

The AI generates a structured report containing:

* Introduction
* Key Findings
* Conclusion
* Sources

### 4. Research Critic

The generated report is passed to the Critic Chain.

The critic evaluates the report and provides:

* Score
* Strengths
* Areas to Improve
* One-line Verdict

## 🛠️ Tech Stack

### AI & LLM

* Python
* Groq
* `openai/gpt-oss-20b`
* LangChain
* LangGraph

### Agents & Tools

* LangChain Agents
* Tavily
* BeautifulSoup
* Requests

### Frontend

* Streamlit

### Environment & Deployment

* Python
* Git
* GitHub
* Streamlit Community Cloud

## 📂 Project Structure

```text
Multi-Agent-Research-System/
│
├── app.py
├── agents.py
├── tools.py
├── pipeline.py
├── requirements.txt
├── README.md
├── .gitignore
└── .env
```

## ⚙️ Installation

### 1. Clone the Repository

```bash
git clone https://github.com/Izmawarakhan/Multi-Agent-Research-System.git
```

```bash
cd Multi-Agent-Research-System
```

### 2. Create a Virtual Environment

```bash
python -m venv .venv
```

### 3. Activate the Environment

**Windows PowerShell:**

```powershell
.venv\Scripts\Activate.ps1
```

### 4. Install Dependencies

```bash
pip install -r requirements.txt
```

### 5. Configure API Keys

Create a `.env` file in the project root:

```env
GROQ_API_KEY=your_groq_api_key
TAVILY_API_KEY=your_tavily_api_key
```

### 6. Run the Application

```bash
streamlit run app.py
```

The application will open in your browser.

## 🔐 Environment Variables

The project requires the following API keys:

| Variable         | Purpose            |
| ---------------- | ------------------ |
| `GROQ_API_KEY`   | Access to Groq LLM |
| `TAVILY_API_KEY` | Web search         |

For Streamlit Cloud deployment, add these values through **Streamlit Secrets** instead of committing `.env` to GitHub.

## 📊 Example Workflow

```text
User enters:
"What is the impact of AI on software engineering?"

        ↓

Search Agent

        ↓

Tavily Web Search

        ↓

Relevant URLs + Snippets

        ↓

Reader Agent

        ↓

BeautifulSoup Web Scraping

        ↓

Research Writer

        ↓

Structured Research Report

        ↓

Research Critic

        ↓

Feedback + Score
```

## 🎯 Project Goals

The main goal of this project is to demonstrate how multiple AI components can work together to automate a real-world research workflow.

Instead of relying on a single LLM response, the system separates the research process into different stages:

**Search → Read → Write → Critique**

This improves the overall research workflow by giving each component a specific responsibility.

## 👩‍💻 Author

**Izma Wara Khan**

Software Engineer | AI/ML & Generative AI

🔗 GitHub:
https://github.com/Izmawarakhan

🔗 LinkedIn:
https://linkedin.com/in/izma-wara-khan

## 📄 License

This project is intended for educational and research purposes.
