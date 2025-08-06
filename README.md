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
- ⚠️ Can trigger function calls like `send_alert()` if risky clauses are found

---

## 🛠 Tech Stack

- [Streamlit](https://streamlit.io/) – for interactive UI
- [OpenAI GPT-4](https://openai.com) – for LLM-based Q&A
- [LangChain](https://www.langchain.com/) – for chaining RAG + tools
- [FAISS](https://github.com/facebookresearch/faiss) – for vector search
- [PyMuPDF](https://pymupdf.readthedocs.io/en/latest/) – for PDF text extraction

---

## 📘 Core Components

### 🔹 Prompting

LawBot uses prompt engineering following the **RTFC framework**:

- **Role** – Sets the model as a legal assistant
- **Task** – Extract, summarize, or answer legal questions
- **Format** – Specifies the output format (JSON, table, plain text)
- **Context** – Includes relevant document text retrieved by RAG

> **Example Prompt:**
>
> ```
> You are a legal assistant.
> Extract all refund-related clauses from the following contract text.
> Return the result in JSON format with keys: clause_type and text.
> Context: "The customer may request a refund within 30 days..."
> ```

---

### 🔹 Structured Output

LawBot returns results in structured formats like **JSON** or **tables** for:

- Easier parsing and UI rendering
- Downstream use (e.g., alert triggers)
- Better explainability

> **Example Output:**
>
> ```json
> {
>   "clause_type": "Termination",
>   "text": "Either party may terminate the agreement with 30 days’ written notice."
> }
> ```

---

### 🔹 Function Calling

Using OpenAI's function calling, LawBot can trigger real actions like:

- `send_alert()` – when risky clauses are detected
- `generate_summary()` – for quick overviews
- `recommend_rewrite()` – for unclear or risky clauses

This makes the assistant **actionable**, not just conversational.

---

### 🔹 Retrieval-Augmented Generation (RAG)

Instead of relying only on memory, LawBot uses **RAG** to fetch accurate information from the uploaded legal document:

1. 📄 The PDF is split into text chunks
2. 🔍 Each chunk is converted into embeddings using OpenAI
3. 🧠 The chunks are stored in a vector database (FAISS or ChromaDB)
4. 🎯 Based on the user’s question, top-matching chunks are retrieved
5. 🤖 GPT uses the retrieved context to generate a grounded, accurate response

This makes answers:

- More trustworthy
- Document-grounded
- Less likely to hallucinate

---
