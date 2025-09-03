# Project Requirements

## Backend Requirements (Python)

### Core Dependencies
- Python 3.8+
- fastapi>=0.95.0,<0.96.0
- uvicorn>=0.22.0,<0.23.0
- sqlalchemy>=1.4.0,<2.0.0
- pydantic>=1.10.7,<2.0.0
- python-dotenv>=0.19.0,<0.20.0
- pydantic-settings>=2.0.0

### Authentication & Security
- python-jose[cryptography]>=3.3.0,<4.0.0
- passlib[bcrypt]>=1.7.4,<2.0.0
- python-multipart>=0.0.5,<0.0.6

### AI & Vector Database
- langchain==0.0.325
- chromadb==0.4.18
- sentence-transformers

### API & WebSockets
- fastapi-cors==0.0.6
- websockets>=10.0,<11.0

## Frontend Requirements (Node.js)

### Core Dependencies
- Node.js 16+
- react@^18.2.0
- react-dom@^18.2.0
- react-router-dom@^6.19.0

### UI Components
- @mui/material@^5.14.18
- @mui/icons-material@^5.14.18
- @emotion/react@^11.11.1
- @emotion/styled@^11.11.0
- react-icons@^5.5.0

### Utilities
- axios@^1.11.0
- react-markdown@^9.0.1
- react-syntax-highlighter@^15.5.0

### Development Dependencies
- @vitejs/plugin-react@^5.0.0
- eslint@^9.33.0
- @types/react@^19.1.10
- @types/react-dom@^19.1.7
- @eslint/js@^9.33.0

## System Requirements

### Backend
- PostgreSQL database
- ChromaDB for vector storage
- Python 3.8+ environment

### Frontend
- Node.js 16+
- npm or yarn package manager

## Environment Variables

### Backend (`.env` file)
```env
DATABASE_URL=postgresql://username:password@localhost:5432/dbname
SECRET_KEY=your-secret-key-here
FRONTEND_URL=http://localhost:3000
OLLAMA_BASE_URL=http://localhost:11434  # Optional
OLLAMA_MODEL=llama2  # Optional
EMBEDDING_MODEL=sentence-transformers/all-MiniLM-L6-v2
CHROMA_PERSIST_DIRECTORY=./chroma_db
```

## Installation

### Backend Setup
```bash
# Navigate to backend directory
cd backend

# Create and activate virtual environment
python -m venv venv
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Set up environment variables
cp .env.example .env  # Edit .env with your settings

# Run database migrations
alembic upgrade head

# Start the backend server
uvicorn app.main:app --reload
```

### Frontend Setup
```bash
# Navigate to frontend directory
cd frontend

# Install dependencies
npm install

# Start the development server
npm run dev
```

## Project Structure

```
project-root/
├── backend/               # Backend code
│   ├── app/               # Main application package
│   ├── database/          # Database migrations and scripts
│   ├── chroma_db/         # Vector database storage
│   ├── .env               # Environment variables
│   └── requirements.txt   # Python dependencies
│
└── frontend/             # Frontend code
    ├── src/              # Source files
    │   ├── components/   # React components
    │   ├── pages/        # Page components
    │   └── App.js        # Main app component
    └── package.json      # Node.js dependencies
```

## Running the Application

1. Start the backend server:
   ```bash
   cd backend
   uvicorn app.main:app --reload
   ```

2. Start the frontend development server:
   ```bash
   cd frontend
   npm run dev
   ```

3. Access the application at `http://localhost:3000`

## Additional Notes

- The backend API will be available at `http://localhost:8000`
- API documentation (Swagger UI) is available at `http://localhost:8000/docs`
- Make sure PostgreSQL is running before starting the backend
- For production, use a proper WSGI server like Gunicorn with Uvicorn workers
