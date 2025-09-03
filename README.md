# AI Chatbot with FastAPI, Ollama, and React

This project implements an AI chatbot using FastAPI for the backend, Ollama models for AI capabilities, vector embeddings with sentence_transformers, ChromaDB for vector storage, and a React frontend.

## Project Structure

```
├── backend/
│   ├── app/
│   │   ├── api/
│   │   ├── core/
│   │   ├── db/
│   │   ├── models/
│   │   ├── services/
│   │   └── main.py
│   ├── requirements.txt
│   └── run.py
└── frontend/
    ├── src/
    │   ├── components/
    │   ├── pages/
    │   ├── services/
    │   └── App.js
    └── package.json
```

## Prerequisites

- Python 3.8+
- Node.js 14+
- PostgreSQL database
- Ollama installed locally or accessible via API

## Backend Setup

1. Navigate to the backend directory:
   ```
   cd backend
   ```

2. Create a virtual environment:
   ```
   python -m venv venv
   ```

3. Activate the virtual environment:
   - Windows: `venv\Scripts\activate`
   - macOS/Linux: `source venv/bin/activate`

4. Install dependencies:
   ```
   pip install -r requirements.txt
   ```

5. Create a `.env` file in the backend directory with the following variables:
   ```
   DATABASE_URL=postgresql+pg8000://postgres:postgres@localhost:5432/postgres
   OLLAMA_BASE_URL=http://localhost:11434
   OLLAMA_MODEL=llama2
   CHROMA_PERSIST_DIRECTORY=./chroma_db
   EMBEDDING_MODEL=sentence-transformers/all-MiniLM-L6-v2
   ```

6. Run the backend server:
   ```
   python run.py
   ```

## Frontend Setup

1. Navigate to the frontend directory:
   ```
   cd frontend
   ```

2. Install dependencies:
   ```
   npm install
   ```

3. Create a `.env` file in the frontend directory with the following variables:
   ```
   REACT_APP_API_URL=http://localhost:8000/api
   ```

4. Start the development server:
   ```
   npm start
   ```

## Features

- Chat with AI using Ollama models
- Upload and manage knowledge base documents
- Vector search for relevant context during conversations
- Conversation history tracking
- Responsive UI with Material-UI components

## Database

The application uses PostgreSQL with the following tables:
- `conversations`: Stores chat conversations
- `messages`: Stores individual chat messages
- `documents`: Stores knowledge base documents

## Vector Storage

Document embeddings are stored in ChromaDB for efficient similarity search.

## API Endpoints

- `/api/chat`: Send and receive chat messages
- `/api/conversations`: Manage conversations
- `/api/documents`: Manage knowledge base documents
- `/api/search`: Search for similar documents