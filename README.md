

# RAG Learning

A simple Retrieval-Augmented Generation (RAG) application built with **Spring Boot**, **Ollama**, and **pgvector**.

This project allows users to:
- Upload documents (PDFs) for semantic search
- Ask questions based on those documents
- Get contextual answers via integrated LLMs

---

## 🚀 Tech Stack

- **Backend**: Spring Boot 3.x
- **LLM**: Ollama (e.g., Mistral, LLaMA2)
- **Embeddings**: `mxbai-embed-large` (via Ollama)
- **Vector DB**: pgvector + PostgreSQL (Docker)
- **Frontend**: [To be added]
- **Build Tool**: Maven

---
## 🧠 RAG Architecture

![RAG Architecture](https://miro.medium.com/v2/resize:fit:636/1*bvAJ2fjCpimJW_JeEV0VDg.png)

A high-level overview of how Retrieval-Augmented Generation works in this project.
---
## ⚙️ Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/NikhilSingh2310/rag-learning.git
cd rag-learning
```

### 2. Start PostgreSQL with pgvector

```bash
docker-compose up -d
```

> Don't use `-v` with `docker-compose down` unless you want to clear your volume data.

### 3. Pull Ollama models

```bash
ollama pull mistral
ollama pull mxbai-embed-large
```

### 4. Run the application

```bash
./mvnw spring-boot:run
```

---

### Ask a Question

```http
POST api/chat
Content-Type: application/json

{
  "message": "What is Spring Boot?"
}
```

---


## 🗂️ Docker Volume Setup

Ensure your `docker-compose.yml` mounts the data properly to persist vectors:

```yaml
volumes:
  - ./volume-data/postgres:/var/lib/postgresql/data
```

---

## ✅ Features

- [x] File Upload and Embedding
- [x] RAG Chat Interface
- [x] Ollama LLM Integration

---

## 👨‍💻 Author

**Nikhil Singh**  
[GitHub](https://github.com/NikhilSingh2310)

