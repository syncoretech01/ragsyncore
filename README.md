
# Syncore RAG API

This repository contains a Python Flask-based Retrieval-Augmented Generation (RAG) API designed to work with Pinecone and OpenAI. It is structured to support direct integration with Voiceflow for conversational AI workflows.

---

## 🌐 Features

- Fast Flask API with CORS
- Embedding-based semantic search using Pinecone
- GPT-powered responses using OpenAI API
- Preprocessing and reranking for improved relevance
- Optimized endpoints for Voiceflow chatbot integration
- Health check and query context endpoint

---

## 📁 Folder Structure

```
├── app.py                  # Main API server
├── text_chunker.py         # Script for chunking and preparing documents
├── embed_to_pinecone.py    # Script to index chunks to Pinecone
├── requirements.txt        # Python dependencies
├── .env.example            # Sample environment file
```

---

## 🧪 Environment Variables

Rename `.env.example` to `.env` and provide your credentials:

```
OPENAI_API_KEY=your_openai_key
PINECONE_API_KEY=your_pinecone_key
PINECONE_ENVIRONMENT=your_pinecone_env
PINECONE_INDEX_NAME=syncoretech-index
PINECONE_NAMESPACE=syncore-rag
```

---

## 🚀 How to Deploy on Render

1. **Repository Setup**:
   - Push all project files to a GitHub repo.
   - Include: `app.py`, `text_chunker.py`, `embed_to_pinecone.py`, `requirements.txt`, `.env.example`

2. **Create Web Service on Render**:
   - **Environment**: Python 3.10 or later
   - **Start Command**: `python app.py`
   - **Build Command**: `pip install -r requirements.txt`
   - **Root Directory**: Leave blank if all files are in root

3. **Set Environment Variables** on Render Dashboard using `.env.example` template.

---

## 🧠 Endpoints

### `/query` (POST)
Enhanced query endpoint for retrieving relevant chunks from Pinecone.

### `/voiceflow/query` (POST)
Voiceflow-friendly query for conversational use cases.

### `/voiceflow/categories` (GET)
Returns static categories to support Voiceflow conversation flows.

### `/health` (GET)
Basic health check.

### `/query_with_context` (POST)
RAG endpoint with support for message history and metadata filters.

---

## 🛠️ Run Locally

```bash
pip install -r requirements.txt
python app.py
```

---

## 🗣 Example Voiceflow Call

```
POST https://your-render-app.onrender.com/voiceflow/query
Body: { "question": "What digital services does Syncore Tech offer?" }
```

---

## 📄 License

MIT License. © 2025 Syncore Tech.
