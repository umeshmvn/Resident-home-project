# 🔎 Resident Home Project 💬✨

![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)
![Flutter](https://img.shields.io/badge/Flutter-3.19-blue)
![FastAPI](https://img.shields.io/badge/FastAPI-Backend-brightgreen)
![Gemini](https://img.shields.io/badge/Gemini-Pro-lightgrey)
![Tavily](https://img.shields.io/badge/Tavily-Search-blue)

## 🌐 Overview

This project is a **Perplexity.ai-inspired AI search assistant** that combines **live web search**, **LLM-powered summarization**, and **a streaming chat experience**. Built using **Flutter** for the frontend and **FastAPI** for the backend, the system delivers real-time answers to user queries via WebSockets and **Google Gemini Pro**.

We also leverage **Tavily's web search API**, and re-rank results using **MiniLM sentence embeddings**, ensuring only the most relevant sources are passed to the LLM.

> 🚀 Whether you're building the next-gen search assistant, a personalized AI researcher, or a study assistant — this open-source project can kickstart it for you!

---

## 🎯 Key Features

- 🔍 **Real-Time Web Search**: Queries are fetched using the Tavily API.
- 🧠 **LLM (Gemini Pro)**: Generates thoughtful, citation-backed responses using structured prompts.
- 📊 **Cosine Similarity Re-ranking**: Uses sentence-transformers to score and sort search results.
- 🌐 **WebSocket Streaming**: Gemini responses stream chunk-by-chunk in real time to the UI.
- 📱 **Cross-platform Flutter UI**: Fully responsive design for web, desktop, and mobile.

---

## 📂 Project Structure

| Folder / File               | Description                                                                 |
|-----------------------------|-----------------------------------------------------------------------------|
| `lib/`                      | Flutter frontend with WebSocket client, chat page, markdown renderer        |
| `server/`                   | FastAPI backend serving REST & WebSocket APIs                               |
| `services/`                 | LLM service (Gemini), search reranker, Tavily integration                   |
| `.env`                      | Secrets like TAVILY_API_KEY and GEMINI_API_KEY                              |
| `main.py`                   | Entry point for the FastAPI backend                                         |
| `pubspec.yaml`              | Flutter dependencies                                                        |
| `screenshot.png`            | Demo UI preview                                                             |

---

## ⚙️ Prerequisites

### ✅ Backend

- 🐍 Python 3.10+
- ⚡ FastAPI
- 🔌 Uvicorn
- 📚 Sentence Transformers
- 🌍 Tavily API key
- 🔑 Gemini API key

### ✅ Frontend

- 🚀 Flutter 3.19+
- Web or Android/iOS device/emulator

---

## 🛠️ Setup & Installation

### 🧪 Backend (FastAPI)

1. **Create a Python virtual environment**

```bash
cd server
python -m venv venv
venv\Scripts\activate  # Windows
```

2. **Install dependencies**
```bash
pip install -r requirements.txt
```
3. **Create .env file in the server/ folder**
```bash
TAVILY_API_KEY=your_tavily_api_key
GEMINI_API_KEY=your_gemini_api_key
```
4. **Run the FastAPI server**
```bash
uvicorn main:app --reload --port 8000
```
## 💻 Frontend (Flutter)
```bash
cd lib
flutter pub get
```
**Run the App server**
```bash
flutter run -d chrome      # Or -d windows / -d android / -d ios
'''
---

### 🧠 How It Works

User enters a query (e.g., "What is LLM?") in the Flutter UI.

The query is sent to the backend via WebSocket.

Tavily performs a real-time web search.

Search results are reranked using cosine similarity via MiniLM embeddings.

The reranked context is sent to Gemini Pro with a structured prompt.

Gemini generates a response, streamed chunk-by-chunk via WebSocket.

Flutter displays streamed content live as it arrives.
