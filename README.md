# RAG-Pipeline-Chatbot-n8n-

RAG Pipeline & Chatbot using n8n + Google Gemini

This repository contains my implementation of a Retrieval-Augmented Generation (RAG) pipeline and chatbot using n8n
. The project connects Google Drive, Pinecone, and Google Gemini API to build an interactive chatbot that can fetch and answer queries from documents in real-time.

⚡ What is n8n?

n8n
 is an open-source workflow automation tool that lets you connect apps, APIs, and databases through visual workflows. It’s highly flexible, developer-friendly, and supports advanced automation without writing complex boilerplate code.

📚 What is RAG (Retrieval-Augmented Generation)?

RAG is an AI architecture that enhances LLMs by retrieving context from a vector database before generating a response.

Store data as embeddings in a vector database (Pinecone).

Retrieve relevant documents when a user asks a question.

Send both query + retrieved docs to an LLM (Google Gemini) for a contextual, accurate answer.

This ensures:
✅ Reliable responses
✅ Fresh knowledge beyond the LLM’s training cutoff
✅ Domain-specific intelligence

🛠️ Tech Stack

n8n (self-hosted via Docker) – Workflow automation engine

Google Drive API – Document source

Pinecone – Vector database for embeddings

Google Gemini API – Embeddings + Chat model

OpenRouter API – Optional chat model integration

Recursive Character Text Splitter – Splits text into chunks

AI Agent (n8n) – Orchestrates retrieval + response generation

⚙️ Workflow Overview
🔹 Document Ingestion Pipeline

Google Drive Trigger → Detect new/updated files.

Download File → Pull document into n8n.

Default Data Loader → Read and process document.

Recursive Text Splitter → Break into smaller chunks.

Embeddings (Google Gemini) → Convert chunks into vectors.

Store in Pinecone → Save embeddings for retrieval.

🔹 Chatbot Pipeline

Chat Message Trigger → User asks a question.

Retrieve from Pinecone → Find most relevant chunks.

AI Agent (n8n) → Combines user query + context.

Google Gemini LLM → Generates contextual response.

Return Answer → Sends reply back to chat interface.
