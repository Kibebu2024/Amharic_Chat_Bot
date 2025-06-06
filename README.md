# 🤖 Full-Stack AI Chatbot App

A production-ready chatbot built with **React + FastAPI + OpenAI + Docker**, complete with feedback collection, admin dashboard, database, CI/CD, and cloud deployment support.

---

## 🛠 Tech Stack
- **Frontend**: React (Chat UI)
- **Backend**: FastAPI (API & OpenAI integration)
- **Database**: SQLite via SQLAlchemy
- **Admin Dashboard**: Streamlit (for feedback monitoring)
- **Containerization**: Docker + docker-compose
- **CI/CD**: GitHub Actions

---

## 🚀 Quick Start (Local with Docker)

1. **Clone the repo**
```bash
git clone https://github.com/your-username/chatbot-app.git
cd chatbot-app
```

2. **Create `.env` file**
```bash
cp .env.example .env
```
Edit `.env` to include your `OPENAI_API_KEY`.

3. **Run the app**
```bash
docker-compose up --build
```
- Frontend: [http://localhost:3000](http://localhost:3000)
- Backend: [http://localhost:8000/docs](http://localhost:8000/docs)

---

## 📊 Admin Dashboard (Streamlit)
```bash
streamlit run dashboard.py
```

---

## ✅ Test Endpoints
```bash
pytest test_main.py
```

---

## 🐳 DockerHub Setup
1. Create an account on [DockerHub](https://hub.docker.com/)
2. Create a public or private repository for `chatbot-backend` and `chatbot-frontend`
3. Add your DockerHub credentials to GitHub Actions secrets:
   - `DOCKER_USERNAME`
   - `DOCKER_PASSWORD`

---

## 🌐 Deploy on Render (Recommended)

.render.yaml — Infrastructure as Code for Render Deployment

services:

type: web name: chatbot-backend env: python buildCommand: "pip install -r requirements.txt" startCommand: "uvicorn app.main:app --host 0.0.0.0 --port 10000" envVars:

key: OPENAI_API_KEY sync: false

key: FRONTEND_ORIGIN value: https://chatbot-frontend.onrender.com plan: free autoDeploy: true


type: static name: chatbot-frontend buildCommand: "npm install && npm run build" staticPublishPath: build env: node plan: free autoDeploy: true


## 📁 Project Structure
```
.
├── backend
│   ├── main.py
│   ├── db.py
│   ├── models.py
│   ├── test_main.py
├── frontend
│   ├── ChatBotPanel.jsx
│   ├── Dockerfile
│   └── ...
├── dashboard.py
├── docker-compose.yml
├── Dockerfile (backend)
├── .env.example
└── .github/workflows/deploy.yml
```

---

## 🙌 Credits
Built with 💙 using OpenAI + FastAPI + React.

> Ready to deploy and scale. Plug in your OpenAI API key and go!
