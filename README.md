# 📜 LawBot: Legal Document Assistant

LawBot is an intelligent assistant that helps users analyze legal documents like contracts, terms of service, or privacy policies using modern LLM techniques.

It combines:

- 🔍 Retrieval-Augmented Generation (RAG)
- 💬 Prompt Engineering
- 📊 Structured Output (JSON/tables)
- ⚙️ Function Calling (to trigger actions based on clause analysis)

---

## 🚀 Features

- 📎 Upload and parse PDF legal documents
- 🤖 Ask natural language questions about contract content
- 🧠 Uses RAG to find the most relevant chunks of information
- 🗂 Returns answers in structured JSON/table format
- ⚠️ Can trigger function calls like `send_alert()` if risky clauses found

---

## 🛠 Tech Stack

- [Streamlit](https://streamlit.io/) – for interactive UI
- [OpenAI GPT-4](https://openai.com) – for LLM-based Q&A
- [LangChain](https://www.langchain.com/) – for chaining RAG + tools
- [FAISS](https://github.com/facebookresearch/faiss) – for vector search
- [PyMuPDF](https://pymupdf.readthedocs.io/en/latest/) – for PDF text extraction

---
