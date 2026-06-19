# 📄 Enterprise Document Intelligence Assistant (RAG)

> An AI-powered document Q&A system built using Retrieval-Augmented Generation (RAG) — enabling users to query large collections of enterprise PDFs with accurate, source-backed answers.

---

## 🚀 Demo
> _Coming soon — will be updated with screenshots and live demo link_

---

## 🧠 About The Project

Traditional document search relies on keyword matching — which often fails to understand context. This project solves that by building a **RAG pipeline** that:

1. Ingests enterprise PDF documents
2. Chunks and embeds them into a vector database (FAISS)
3. Retrieves the most relevant context for any user query
4. Passes that context to an LLM (OpenAI GPT) to generate accurate, grounded answers

This eliminates hallucinations and ensures every answer is traceable back to a source document.

---

## ⚙️ Tech Stack

| Layer | Technology |
|---|---|
| Language | Python |
| AI Orchestration | LangChain |
| LLM | OpenAI API (GPT-3.5 / GPT-4) |
| Vector Store | FAISS, ChromaDB |
| Embeddings | OpenAI Embeddings |
| Backend API | FastAPI |
| PDF Processing | PyMuPDF, PDFPlumber |
| Frontend (planned) | Streamlit |

---

## ✨ Features

- 📥 Upload and ingest 50+ enterprise PDFs
- 🔍 Semantic search using vector embeddings
- 💬 Natural language Q&A with source attribution
- 🧩 Metadata filtering for targeted document search
- 🪟 Sliding-window chunking with overlap for better retrieval precision
- 🚫 Hallucination reduction via retrieval-grounded responses

---

## 🏗️ Architecture

```
User Query
    ↓
FastAPI Backend
    ↓
Query Embedding (OpenAI)
    ↓
FAISS Vector Store → Top-K Relevant Chunks
    ↓
LangChain RAG Chain → LLM (GPT)
    ↓
Answer + Source Reference
```

---

## 📁 Project Structure

```
enterprise-doc-assistant/
├── app/
│   ├── main.py          # FastAPI app entry point
│   ├── ingestor.py      # PDF loading & chunking
│   ├── embedder.py      # Embedding generation
│   ├── retriever.py     # FAISS vector search
│   └── chain.py         # LangChain RAG chain
├── data/
│   └── pdfs/            # Upload PDFs here
├── vectorstore/         # FAISS index storage
├── requirements.txt
└── README.md
```

---

## 🛠️ Setup & Installation

```bash
# Clone the repo
git clone https://github.com/sarthakt86/sarthakt86.git
cd enterprise-doc-assistant

# Create virtual environment
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Set environment variables
export OPENAI_API_KEY=your_openai_api_key

# Run the app
uvicorn app.main:app --reload
```

---

## 📌 API Endpoints

| Method | Endpoint | Description |
|---|---|---|
| POST | `/upload` | Upload PDF documents |
| POST | `/query` | Ask a question |
| GET | `/sources` | List indexed documents |

---

## 🗺️ Roadmap

- [x] RAG pipeline with FAISS
- [x] FastAPI backend
- [ ] Streamlit frontend UI
- [ ] Multi-user support
- [ ] Fine-tuned embedding model
- [ ] Docker containerization
- [ ] Deploy on AWS EC2

---

## 👨‍💻 Author

**Sarthak Tiwary**
- 📧 sarthaktiwary01@gmail.com
- 🔗 [LinkedIn](https://www.linkedin.com/in/sarthak-tiwary-4b7639237/)
- 🐙 [GitHub](https://github.com/sarthakt86/sarthakt86)
