# FDA MAUDE RAG Chatbot for Glucose Monitoring Device Safety Analysis

## 📌 Overview
This repository implements a Retrieval-Augmented Generation (RAG) pipeline for querying FDA MAUDE adverse event reports related to Glucose Monitoring systems. The system integrates anomaly detection, semantic search, reranking, and a regulatory-style chatbot interface.

---

## 📂 Repository Structure

- **`RAG_pipeline_Chatbot.ipynb`** – Main notebook implementing the RAG pipeline and chatbot interface. Integrates semantic search using Qdrant, cross-encoder reranking, and response generation with a locally hosted **Mistral 7B** model via **Ollama**. Includes a **Gradio**-based UI for user interaction.

- **`Qdrant_upsert.ipynb`** – Handles generation of sentence embeddings for FOI narratives and upserts them into a Qdrant vector store, along with structured metadata.

- **`README.md`** – Provides an overview of the repository, setup instructions, and usage guidelines.

---

## 🛠 Setup & Requirements

### 1️⃣ Install Python
Ensure **Python 3.11.4** is installed.

### 2️⃣ Start the LLM
Run the **Mistral 7B** model locally via **Ollama**:
```bash
ollama run mistral
```

### 3️⃣ Install Dependencies
```bash
pip install sentence-transformers qdrant-client gradio
```
(Also install any additional modules listed in `RAG_pipeline_Chatbot.ipynb`.)

---

## ▶ How to Run the Chatbot

1. Start **Mistral 7B** locally via Ollama.
2. Open and run all cells in `RAG_pipeline_Chatbot.ipynb`.
3. At the end of execution, a **local link** and a **public Gradio link** will be generated.
4. Open either link in your browser.
5. Enter a query (e.g., `Events where Death Occurred`) and view the generated response, which will be grounded in retrieved FDA MAUDE reports.

---

