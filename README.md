# AI RAG Chatbot Automation

An AI-powered RAG (Retrieval-Augmented Generation) chatbot automation built using n8n.

## Features

- Automatic document ingestion from Google Drive
- Document processing and chunking
- Google Gemini Embeddings
- Pinecone Vector Database
- AI Agent chatbot
- Context-aware responses using RAG

## Architecture

### Document Ingestion Pipeline

Google Drive Trigger
→ Download File
→ Default Data Loader
→ Recursive Character Text Splitter
→ Gemini Embeddings
→ Pinecone Vector Store

### Chatbot Pipeline

User Message
→ AI Agent
→ Pinecone Vector Store
→ Relevant Context
→ OpenRouter Chat Model
→ AI Response

## Technologies Used

- n8n
- Google Gemini
- Pinecone
- OpenRouter
- Google Drive
- RAG
- Vector Embeddings

## How It Works

1. Upload a document to Google Drive.
2. Google Drive Trigger detects the new file.
3. The workflow downloads the document.
4. The document is loaded and split into smaller chunks.
5. Gemini creates embeddings for the document chunks.
6. Pinecone stores the embeddings.
7. The user sends a message to the chatbot.
8. The AI Agent searches Pinecone for relevant information.
9. The AI model generates a context-aware response.

## Setup

1. Import the workflow JSON files into n8n.
2. Configure Google Drive credentials.
3. Configure Google Gemini credentials.
4. Configure Pinecone credentials and index.
5. Configure the OpenRouter chat model.
6. Activate the workflows.
7. Upload a document and test the chatbot.

## Workflow Architecture

### RAG Pipeline & Chatbot

![RAG Pipeline and Chatbot](images/RAG-pipeline & chatbot.png.png)

This workflow handles document ingestion, embedding generation, vector storage, and AI-powered question answering.

### n8n RAG Workflow

![n8n RAG Workflow](images/n8n-rag-workflow.png.png)

The workflow uses Google Drive, Gemini Embeddings, Pinecone Vector Store, an AI Agent, and an OpenRouter Chat Model.

## Author

Suraj Mishra
