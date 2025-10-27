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

knowledge-chat-system/
├── app/
│   ├── __init__.py
│   ├── main.py
│   ├── config.py
│   ├── models/
│   │   ├── __init__.py
│   │   ├── database.py
│   │   └── schemas.py
│   ├── routes/
│   │   ├── __init__.py
│   │   ├── auth.py
│   │   ├── documents.py
│   │   └── query.py
│   ├── services/
│   │   ├── __init__.py
│   │   ├── auth_service.py
│   │   ├── document_service.py
│   │   ├── embedding_service.py
│   │   └── query_service.py
│   ├── utils/
│   │   ├── __init__.py
│   │   ├── logger.py
│   │   └── helpers.py
│   └── db/
│       ├── __init__.py
│       └── session.py
├── faiss_indexes/
├── uploads/
├── .env
├── .gitignore
├── requirements.txt
├── Dockerfile
├── docker-compose.yml
└── README.md


---

## ⚡ Getting Started (Local)

### 1. **Clone the Repo**

git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>


### 2. **Set Up Python Environment**
python3 -m venv env
source env/bin/activate
pip install -r requirements.txt


### 3. **Create and Fill `.env`**

Copy `.env.example` to `.env`, then fill in actual secrets such as your OPENAI_API_KEY and DATABASE_URL.

cp .env.example .env

### 4. **Run with Docker (Recommended)**


- This runs the FastAPI backend and Postgres together.

### 5. **Access the API**

Go to: [http://localhost:8000/docs](http://localhost:8000/docs) for Swagger API UI.

---

## 🧑‍💻 Core API Endpoints

**Authentication:**
- `POST /auth/register` – Register a new user
- `POST /auth/login` – Get JWT token

**Documents:**
- `POST /documents/upload` – Upload a document (auth required)
- `GET /documents/` – List uploaded documents for current user

**Query:**
- `POST /query/` – Query your documents (auth required)

Full details/descriptions and example payloads are available at `/docs`.

---

## 📝 .env Example

OPENAI_API_KEY=sk-...
DATABASE_URL=postgresql://postgres:postgres@localhost:5432/knowledge_chat_db
SECRET_KEY=mysecretkey

add other fields as per config.py usage
text


---

## 📦 Deployment

To deploy on Render/Railway:
- Fork or push to your own GitHub repo
- Connect the repo to Render/Railway web backend
- Add production `.env` variables on their dashboard (never store secrets in code)
- Use `docker-compose` or single Dockerfile as needed, or set the command:

uvicorn app.main:app --host 0.0.0.0 --port 10000


---

## 🛠️ Notes

- Folders like `uploads/`, `logs/`, `faiss_indexes/`, `env/`, and `.env` are **gitignored** by default (**never push secrets or user data!**)
- Source code only is stored in git
- For test/demo use, adjust your `.env` and endpoint configs

---

## 🙏 Credits

- Main libraries: FastAPI, SQLAlchemy, FAISS, OpenAI, Uvicorn, Docker
- Assignment from: [Company/Institution Name]
- Docs generated on: [date]

---

Feel free to reach out for clarifications or improvements.
