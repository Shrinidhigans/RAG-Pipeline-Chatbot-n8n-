# RAG-Pipeline-Chatbot-n8n-
# RAG Pipeline & Chatbot using n8n + Google Gemini

This repository contains my implementation of a **Retrieval-Augmented Generation (RAG) pipeline and chatbot** using [n8n](https://n8n.io/).  
The project connects **Google Drive, Pinecone, and Google Gemini API** to build an interactive chatbot that fetches and answers queries from documents in real time.

---

## ⚡ What is n8n?

[n8n](https://n8n.io/) is an **open-source workflow automation tool** that lets you connect apps, APIs, and databases through visual workflows.  
It’s highly flexible, developer-friendly, and makes building data pipelines easier without needing heavy coding.

---

## 📚 What is RAG?

**Retrieval-Augmented Generation (RAG)** enhances LLMs by retrieving context before generating an answer:

1. **Store** documents as embeddings in a vector database (Pinecone).  
2. **Retrieve** relevant chunks when a user asks a question.  
3. **Generate** context-aware answers using Google Gemini.  

This ensures:
- ✅ More accurate answers  
- ✅ Knowledge beyond the LLM’s training cutoff  
- ✅ Domain-specific intelligence  

---

## 🛠️ Tech Stack

- **n8n (Docker self-hosted)** – workflow engine  
- **Google Drive API** – source for documents  
- **Pinecone** – vector database for embeddings  
- **Google Gemini API** – embeddings + chat model  
- **OpenRouter API** – optional chat model integration  
- **Recursive Character Text Splitter** – splits text into chunks  
- **AI Agent (n8n)** – orchestrates retrieval + response  

---

## ⚙️ Workflow Overview

---

## ⚙️ Workflow Overview

### 🔹 Document Ingestion Pipeline
- Trigger: Google Drive file creation  
- Download document  
- Load + split text into chunks  
- Generate embeddings with **Google Gemini**  
- Store vectors in **Pinecone**  

### 🔹 Chatbot Pipeline
- Trigger: chat message  
- Retrieve relevant chunks from Pinecone  
- AI Agent combines query + context  
- **Google Gemini** generates a response  
- Return final answer to user

  
 ## 🖼️ Architecture
![Pipeline](./docs/architecture.png)

---

## 🌟 Features
- Automated ingestion from **Google Drive**  
- Embeddings with **Google Gemini**  
- Vector search using **Pinecone**  
- Interactive chatbot with memory  
- Modular and extensible workflows  

---

## 🔮 Future Enhancements
- Web-based chatbot frontend  
- Multi-user context handling  
- More data sources (Slack, Notion, Email, etc.)  

---

## 💡 Reflections
This project was an **amazing learning experience**.  

I got hands-on with:  
- Running **n8n locally via Docker**  
- Designing a **RAG pipeline end to end**  
- Using **Google Gemini API** for embeddings + chat  
- Integrating **Pinecone** into a live workflow  

It helped me understand how **automation + vector search + LLMs** can be combined into practical, scalable systems.  
I really enjoyed building this—it was both challenging and rewarding.  

---

## 👨‍💻 Author
Built with ❤️ using **n8n + Google Gemini API + Pinecone**  
by *Shrinidhi*

