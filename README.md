# 🚀 AI-Powered Code Review & Bug Detection Platform

An advanced, AI-driven platform that automatically analyzes GitHub repositories, detects bugs, identifies security vulnerabilities, explains code in natural language, and provides actionable refactoring suggestions — all powered by static analysis + machine learning models like CodeBERT.

---

## ✅ Features

### 🔹 Core (MVP)
- Submit a GitHub repository URL
- Fetch and analyze source code automatically
- Static analysis (linting, style issues, unused variables, unreachable code)
- Cyclomatic complexity scoring
- Per-file and per-function insights
- Fully asynchronous job queue for large repos
- Clean and structured analysis reports

### 🔹 AI Enhancements
- ML-based bug prediction using CodeBERT / CodeT5
- AI-generated code explanations
- Design pattern recommendations
- Security vulnerability scanning (OWASP-aligned)
- Refactoring suggestions with sample fixes
- Automated pull request review comments

### 🔹 Enterprise Features
- Private repo access via GitHub OAuth
- Team dashboards and role-based access
- Trend analysis and commit-level quality scoring
- PDF exportable reports
- CI/CD integration-ready REST API

---

## 🏗️ System Architecture

```
+-----------------+        +------------------+        +------------------------+
|     Frontend     | --->   |  Spring Boot API | --->   |   Python AI Engine     |
|   (React/TW)     |        |   (Auth, Jobs)   |        | (Static + ML Analysis) |
+-----------------+        +------------------+        +------------------------+
                                    |
                                    v
                          +-----------------------+
                          |      PostgreSQL       |
                          +-----------------------+
                                    |
                                    v
                          +-----------------------+
                          |      GitHub API       |
                          +-----------------------+
```

---

## 🧠 Tech Stack

### Backend
- Spring Boot 3
- Spring Security (JWT)
- Spring Data JPA
- GitHub REST API
- Async executor job queue

### AI / Analysis Engine
- Python 3.11
- FastAPI
- Radon (complexity)
- Bandit, Flake8, Pylint
- HuggingFace Transformers (CodeBERT, CodeT5)
- PyTorch / Scikit-Learn

### Frontend
- React 18
- TailwindCSS
- Recharts (analytics visualizations)

### Database
- PostgreSQL 15
- Flyway migrations

### DevOps
- Docker + Docker Compose
- GitHub Actions CI/CD
- Prometheus + Grafana (monitoring)

---

## 📦 Project Structure

```
ai-code-review-platform/
│
├── backend-spring/
│   ├── src/main/java/...
│   ├── src/main/resources/
│   └── pom.xml
│
├── analysis-engine-python/
│   ├── main.py
│   ├── analyzers/
│   ├── ml/
│   └── requirements.txt
│
├── frontend/
│   ├── public/
│   ├── src/
│   └── package.json
│
├── db/
│   └── migrations/
│
├── docker-compose.yml
└── README.md
```

---

## ⚙️ Installation & Setup

### 1. Clone the repository
```bash
git clone https://github.com/yourusername/ai-code-review-platform.git
cd ai-code-review-platform
```

### 2. Setup environment variables
Create a `.env` file:
```env
GITHUB_TOKEN=your_token
JWT_SECRET=super_secret_key
DB_USER=postgres
DB_PASS=password
DB_NAME=code_review
```

### 3. Start with Docker Compose (recommended)
```bash
docker-compose up --build
```

### 4. Manual local development
#### Backend:
```bash
cd backend-spring
mvn spring-boot:run
```

#### Python AI Engine:
```bash
cd analysis-engine-python
pip install -r requirements.txt
uvicorn main:app --reload
```

#### Frontend:
```bash
cd frontend
npm install
npm run dev
```

---

## 🔥 API Endpoints (Summary)

### Authentication
```
POST /auth/register
POST /auth/login
```

### Code Analysis
```
POST /analyze
GET /results/{jobId}
GET /jobs/{jobId}
```

### Health Checks
```
GET /health
```

---

## 🧪 Testing

### Backend
```bash
mvn test
```

### Python Engine
```bash
pytest -v
```

### Frontend
```bash
npm run test
```

### Load Testing
```bash
locust
```

---

## 🛣️ Roadmap

### Phase 1 — Architecture & Backend Foundation  
### Phase 2 — Static Analysis Engine (Python)  
### Phase 3 — MVP Integration  
### Phase 4 — Frontend Dashboard  
### Phase 5 — AI/ML Bug Detection  
### Phase 6 — PR Bot + Enterprise Features  
### Phase 7 — Performance + Security Hardening  
### Phase 8 — Deployment  
### Phase 9 — Extensions + Plugins  

Full roadmap available in:  
`/docs/PROJECT_PLAN.md`

---

## 🤝 Contributing

We welcome contributions!  
1. Fork the repo  
2. Create a new branch  
3. Commit your changes  
4. Open a pull request  

Follow commit convention:  
```
feat: add new analyzer
fix: resolve null-pointer false positive
chore: refactor queue handler
```

---

## 📄 License

MIT License — free for personal and commercial use.

---

## ⭐ Support

If you like this project, give it a **star** and follow the repo!  