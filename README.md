# 📰 AI-Based News Aggregator

An intelligent news aggregation system powered by **LLMs** and **RAG (Retrieval-Augmented Generation)** that fetches, processes, summarizes, and answers questions about the latest news — all in one place.

---

## 🚀 Features

- 🔍 **Smart News Fetching** — Aggregates news from multiple RSS feeds and APIs
- 🤖 **LLM-Powered Summarization** — Generates concise summaries using large language models
- 📚 **RAG Pipeline** — Ask questions about news articles using retrieval-augmented generation
- 🧠 **Semantic Search** — Find relevant news using vector embeddings
- 🗂️ **Category Filtering** — Filter by topics: Tech, Politics, Sports, Finance, etc.
- 💬 **Conversational Q&A** — Chat with your news feed naturally
- 🔄 **Auto-Refresh** — Scheduled news updates via cron/background tasks

---

## 🏗️ Project Structure

```
ai-news-aggregator/
├── backend/
│   ├── main.py                  # FastAPI app entry point
│   ├── config.py                # Configuration & environment variables
│   ├── models/
│   │   ├── news.py              # News article data models
│   │   └── embeddings.py        # Embedding model wrappers
│   ├── services/
│   │   ├── fetcher.py           # News fetching from RSS/APIs
│   │   ├── summarizer.py        # LLM summarization service
│   │   ├── embedder.py          # Text embedding generation
│   │   └── rag_pipeline.py      # RAG query + retrieval logic
│   ├── database/
│   │   ├── vector_store.py      # Vector DB integration (FAISS/Chroma/Pinecone)
│   │   └── db.py                # SQLite/PostgreSQL connection
│   ├── routers/
│   │   ├── news.py              # /news endpoints
│   │   └── chat.py              # /chat Q&A endpoints
│   └── scheduler.py             # Background task scheduler
├── frontend/
│   ├── index.html               # Main UI
│   ├── app.js                   # Frontend logic
│   └── style.css                # Styling
├── data/
│   ├── raw/                     # Raw fetched articles (JSON)
│   └── vectorstore/             # Persisted vector embeddings
├── notebooks/
│   ├── rag_experiments.ipynb    # RAG pipeline experiments
│   └── llm_evaluation.ipynb     # LLM output evaluation
├── tests/
│   ├── test_fetcher.py
│   ├── test_rag.py
│   └── test_api.py
├── .env.example                 # Environment variable template
├── .gitignore
├── requirements.txt
├── docker-compose.yml
├── Dockerfile
└── README.md
```

---

## ⚙️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Backend | Python, FastAPI |
| LLM | OpenAI GPT-4 / Groq / Ollama |
| Embeddings | OpenAI `text-embedding-3-small` / HuggingFace |
| Vector Store | FAISS / ChromaDB / Pinecone |
| Database | SQLite / PostgreSQL |
| News Sources | NewsAPI, RSS Feeds, GNews |
| Frontend | HTML/CSS/JS or React |
| Deployment | Docker, Render / Railway / AWS |

---

## 🔧 Setup & Installation

### Prerequisites

- Python 3.10+
- pip or conda
- API keys: OpenAI / Groq / NewsAPI

### 1. Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/ai-news-aggregator.git
cd ai-news-aggregator
```

### 2. Create Virtual Environment

```bash
python -m venv venv
source venv/bin/activate        # Linux/Mac
venv\Scripts\activate           # Windows
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure Environment Variables

```bash
cp .env.example .env
# Edit .env and add your API keys
```

### 5. Run the Application

```bash
uvicorn backend.main:app --reload
```

Visit `http://localhost:8000/docs` for the interactive API docs.

---

## 🌐 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/news` | Get latest aggregated news |
| GET | `/news?category=tech` | Filter by category |
| GET | `/news/{id}` | Get article by ID |
| POST | `/news/refresh` | Manually trigger news fetch |
| POST | `/chat` | Ask a question via RAG |
| GET | `/search?q=query` | Semantic search across articles |

---

## 💡 RAG Pipeline Overview

```
User Query
    │
    ▼
Query Embedding (text-embedding model)
    │
    ▼
Vector Search (FAISS / Chroma)
    │
    ▼
Top-K Relevant Articles Retrieved
    │
    ▼
Context + Query → LLM Prompt
    │
    ▼
LLM Response (GPT-4 / Groq / Ollama)
    │
    ▼
Answer with Source Citations
```

---

## 🐳 Docker Deployment

```bash
docker-compose up --build
```

---

## 🔐 Environment Variables

See `.env.example` for all required variables:

```
OPENAI_API_KEY=
NEWSAPI_KEY=
GROQ_API_KEY=
DATABASE_URL=
VECTOR_STORE_PATH=./data/vectorstore
```

---

## 🧪 Running Tests

```bash
pytest tests/ -v
```

---

## 🗺️ Roadmap

- [ ] Multi-language news support
- [ ] User personalization & bookmarks
- [ ] Real-time news streaming via WebSockets
- [ ] Email digest feature
- [ ] Mobile app (React Native)

---

## 🤝 Contributing

Pull requests are welcome! Please open an issue first to discuss major changes.

---

## 📄 License

MIT License — see [LICENSE](LICENSE) for details.

---

## 👤 Author
Suhana Kaushik
