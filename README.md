# Knowledge Chat System

A full-stack backend application that allows users to register, upload documents, and use generative AI to search and answer questions based on their personalized knowledge base. Uses FastAPI, Postgres, Docker, and OpenAI embeddings with a FAISS vector store.

---

## 🚀 Features

- User registration and authentication (JWT-based)
- Secure document upload (txt/pdf)
- Automatic document chunking and OpenAI embedding
- Semantic search using FAISS vector index
- Query natural language questions against your knowledge base and get LLM-based answers
- REST API with automatic Swagger UI docs (`/docs`)

---

## 🗂️ Project Structure

```
knowledge_chat_system/
│
├── app/
│   ├── db/                    # DB session and ORM setup
│   ├── models/                # Pydantic and SQLAlchemy models/schemas
│   │   ├── database.py
│   │   ├── schemas.py
│   ├── routes/                # All API endpoint route definitions
│   │   ├── auth.py
│   │   ├── documents.py
│   │   ├── query.py
│   ├── services/              # Business logic and abstractions
│   │   ├── auth_service.py
│   │   ├── document_service.py
│   │   ├── embedding_service.py
│   │   ├── query_service.py
│   ├── utils/                 # Utility functions (e.g., logger, helpers)
│   ├── config.py              # App-wide config (from .env)
│   ├── main.py                # FastAPI app instance
│
├── uploads/                   # Uploaded user docs (ignored by git)
├── faiss_indexes/             # FAISS vector indexes (ignored by git)
├── logs/                      # Log output (ignored by git)
├── env/                       # Local venv (ignored by git)
│
├── requirements.txt           # Python dependencies
├── Dockerfile                 # For Docker builds
├── docker-compose.yml         # Multi-container orchestration
├── .env.example               # Template for env variables
├── .gitignore
│
└── README.md
```

---

## ⚡ Getting Started (Local Development)

### 1. Clone the Repository

```bash
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>
```

### 2. Set Up Python Virtual Environment

```bash
python3 -m venv env
source env/bin/activate  # On Windows: env\Scripts\activate
pip install -r requirements.txt
```

### 3. Create and Configure `.env` File

```bash
cp .env.example .env
```

Edit `.env` and add your configuration:

```env
OPENAI_API_KEY=sk-your-openai-key-here
DATABASE_URL=postgresql://postgres:postgres@localhost:5432/knowledge_chat_db
SECRET_KEY=your-secret-key-here
ALGORITHM=HS256
ACCESS_TOKEN_EXPIRE_MINUTES=30
```

### 4. Run with Docker Compose (Recommended)

```bash
docker-compose up --build
```

This will:
- Start the FastAPI backend on `http://localhost:8000`
- Start PostgreSQL database on `localhost:5432`
- Create the necessary tables automatically

### 5. Access the API

- **Swagger UI:** http://localhost:8000/docs
- **ReDoc:** http://localhost:8000/redoc

---

## 🧑‍💻 API Endpoints

### Authentication

- **POST** `/auth/register` - Register a new user
  ```json
  {
    "username": "alice",
    "email": "alice@example.com",
    "password": "password123"
  }
  ```

- **POST** `/auth/login` - Login and get JWT token
  ```json
  {
    "username": "alice",
    "password": "password123"
  }
  ```

### Documents

- **POST** `/documents/upload` - Upload a document (requires authentication)
  - Headers: `Authorization: Bearer <token>`
  - Body: Form data with file

- **GET** `/documents/` - List all documents for current user (requires authentication)
  - Headers: `Authorization: Bearer <token>`

### Query

- **POST** `/query/` - Query your documents (requires authentication)
  ```json
  {
    "question": "What is machine learning?",
    "top_k": 3
  }
  ```
  - Headers: `Authorization: Bearer <token>`
  - Response includes: answer, sources, context_used, timestamp

---

## 📝 Example Usage with cURL

### 1. Register a User

```bash
curl -X POST "http://localhost:8000/auth/register" \
  -H "Content-Type: application/json" \
  -d '{
    "username": "alice",
    "email": "alice@example.com",
    "password": "password123"
  }'
```

### 2. Login to Get Token

```bash
curl -X POST "http://localhost:8000/auth/login" \
  -H "Content-Type: application/json" \
  -d '{
    "username": "alice",
    "password": "password123"
  }'
```

### 3. Upload a Document

```bash
curl -X POST "http://localhost:8000/documents/upload" \
  -H "Authorization: Bearer <your_access_token>" \
  -F "file=@document.txt"
```

### 4. Query Your Documents

```bash
curl -X POST "http://localhost:8000/query/" \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer <your_access_token>" \
  -d '{
    "question": "What is the main topic of this document?",
    "top_k": 3
  }'
```

---

## 🐳 Docker Commands

### Start the Application

```bash
docker-compose up --build
```

### View Logs

```bash
docker-compose logs -f fastapi_app
```

### Stop the Application

```bash
docker-compose down
```

### Reset Database

```bash
docker-compose down -v
docker-compose up --build
```

### Access PostgreSQL

```bash
docker-compose exec postgres psql -U postgres -d knowledge_chat_db
```

### View All Documents in Database

```bash
docker-compose exec postgres psql -U postgres -d knowledge_chat_db -c "SELECT id, original_filename, chunk_count FROM documents;"
```

### Reset Database Sequences

```bash
docker-compose exec postgres psql -U postgres -d knowledge_chat_db -c "
DELETE FROM documents;
ALTER SEQUENCE documents_id_seq RESTART WITH 1;
DELETE FROM users;
ALTER SEQUENCE users_id_seq RESTART WITH 1;
"
```

---

## 📦 Deployment on Render/Railway

### 1. Push Code to GitHub

```bash
git init
git add .
git commit -m "Initial commit: Knowledge Chat System"
git branch -M main
git remote add origin https://github.com/<your-username>/<repo-name>.git
git push -u origin main
```

### 2. Deploy on Render

- Go to https://render.com
- Click "New +" → "Web Service"
- Connect your GitHub repository
- Set build command: `pip install -r requirements.txt`
- Set start command: `uvicorn app.main:app --host 0.0.0.0 --port 10000`
- Add environment variables from your `.env` file
- Deploy!

### 3. Deploy on Railway

- Go to https://railway.app
- Click "New Project" → "Deploy from GitHub Repo"
- Select your repository
- Add environment variables
- Set start command: `uvicorn app.main:app --host 0.0.0.0 --port $PORT`
- Deploy!

---

## ⚙️ Configuration

### Environment Variables (.env)

| Variable | Description | Example |
|----------|-------------|---------|
| `OPENAI_API_KEY` | OpenAI API key for embeddings & LLM | `sk-...` |
| `DATABASE_URL` | PostgreSQL connection string | `postgresql://user:pass@host:5432/db` |
| `SECRET_KEY` | JWT secret key | `your-secret-key` |
| `ALGORITHM` | JWT algorithm | `HS256` |
| `ACCESS_TOKEN_EXPIRE_MINUTES` | JWT expiration time | `30` |

---

## 🛠️ Tech Stack

- **Backend Framework:** FastAPI
- **Web Server:** Uvicorn
- **Database:** PostgreSQL with SQLAlchemy ORM
- **Vector Store:** FAISS
- **Embeddings:** OpenAI text-embedding-3-small
- **LLM:** OpenAI GPT-4
- **Authentication:** JWT (PyJWT)
- **Containerization:** Docker & Docker Compose

---

## 📚 Key Features Explained

### 1. User Authentication
- Secure password hashing with bcrypt
- JWT-based token authentication
- Protected endpoints require valid tokens

### 2. Document Management
- Upload and store documents (txt/pdf)
- Automatic chunking into manageable pieces
- OpenAI embeddings for semantic understanding

### 3. Vector Search
- FAISS index for fast similarity search
- Cosine similarity scoring
- Top-K retrieval for context

### 4. AI-Powered Query
- OpenAI GPT-4 for answer generation
- Context-aware responses
- Source attribution

---

## ❌ Common Issues & Solutions

### Issue: "OPENAI_API_KEY not found"
**Solution:** Ensure `.env` file has your OpenAI API key and is loaded properly.

### Issue: "Database connection refused"
**Solution:** Make sure PostgreSQL container is running:
```bash
docker-compose ps
```

### Issue: "Failed to process query"
**Solution:** Check logs and ensure:
- Document is uploaded
- FAISS index exists
- OpenAI API key is valid

---

## 📝 Notes

- **Security:** Never commit `.env` file with real secrets
- **Data:** `uploads/`, `logs/`, and `faiss_indexes/` are ignored by git
- **Testing:** Use `/docs` endpoint to test all APIs interactively
- **Local Development:** Change `DATABASE_URL` if using different Postgres setup

---

## 🤝 Contributing

Feel free to fork, modify, and improve the project. For major changes, please open an issue first.

---

## 📄 License

This project is provided as-is for educational and assignment purposes.

---

## 📧 Support

For issues or questions, please create a GitHub issue or contact the project maintainers.

---

**Last Updated:** October 27, 2025
