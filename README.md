# 🧠 Conversational RAG with History-Aware Question Reformulation (LangChain + Groq)

This repository demonstrates a professional implementation of a **Conversational Retrieval-Augmented Generation (RAG)** system using **LangChain**, powered by **Groq (LLaMA 3)** for fast inference and enhanced with **chat history awareness**.

## 🚀 Features

- 💬 Multi-turn conversational RAG system  
- 🧠 Contextual question reformulation using previous chat history  
- 🔍 Semantic search with HuggingFace embeddings and Chroma vector store  
- ⚡ Powered by Groq API for ultra-fast LLM inference  
- 🧾 Memory support with per-session history management  
- 🔧 Modular and easy to extend with your own data/documents  

---

## 🧱 Tech Stack

| Component         | Technology Used                      |
|------------------|--------------------------------------|
| Language Model    | Groq (LLaMA3-8B) via `langchain_groq` |
| Vector DB         | Chroma                              |
| Embedding Model   | all-MiniLM-L6-v2 (`langchain_huggingface`) |
| Framework         | LangChain                           |
| Chat History Store| In-memory (extendable to Redis etc.)|

---

## 🧩 Architecture

```mermaid
flowchart TD
    A[User Question] --> B[Chat History + Question]
    B --> C[Rephrase Question with LLM]
    C --> D[Retriever Chroma + Embedding]
    D --> E[Relevant Documents]
    E --> F[LLM Answer using Stuff Chain]
    F --> G[Response + Updated History]

project/
├── app.py                         # Main application logic
├── .env                           # API keys and configuration
├── README.md                      # This file
├── requirements.txt               # Python dependencies

