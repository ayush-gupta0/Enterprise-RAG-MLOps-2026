# 🚀 Enterprise RAG Pipeline with MLOps tracking

[![Open In Colab](https://colab.research.google.com/drive/1euq_1DpnkfmxirWU6YyJbQoC8U7E7bBe#scrollTo=6HW_cv3ud5A5)
[![MLflow](https://img.shields.io/badge/MLflow-Tracking-blue)](https://mlflow.org/)
[![Llama 3.1](https://img.shields.io/badge/Model-Llama_3.1-orange)](https://ai.meta.com/blog/meta-llama-3-1/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

An industrial-grade **Retrieval-Augmented Generation (RAG)** system designed for high-speed document intelligence. This project leverages **Llama 3.1 (via Groq)** for reasoning and **MLflow** for rigorous experiment tracking and metric logging.

---

## 🛠️ The Tech Stack
* **LLM Engine:** Llama-3.1-8b-instant (via Groq Cloud)
* **Orchestration:** LangChain (LCEL)
* **Vector Database:** ChromaDB
* **Embeddings:** HuggingFace `all-MiniLM-L6-v2`
* **MLOps:** MLflow (Experiment Tracking & Artifact Logging)
* **Environment:** Google Colab + ngrok (External UI Tunneling)

---

## 🏗️ System Architecture
The pipeline follows a modular **ETL-RAG** workflow to ensure scalability and reproducibility:

1. **Ingestion:** PyPDFLoader chunks large documents into semantic blocks.
2. **Indexing:** Text blocks are converted to vectors and stored in ChromaDB.
3. **Retrieval:** Semantic similarity search fetches top-k relevant context.
4. **Generation:** Llama 3.1 synthesizes a final answer based on retrieved context.
5. **Tracking:** Every run logs chunk size, response time, and model output to MLflow.

---

## 📊 MLOps Dashboard (MLflow)
We use a **Reverse Proxy (ngrok)** to expose the internal MLflow server. This allows stakeholders to review model performance in real-time.

| Parameter | Logged Value | Purpose |
| :--- | :--- | :--- |
| `chunk_size` | 1000 | Controls retrieval granularity |
| `model` | llama-3.1-8b | Primary inference engine |
| `ai_answer.txt` | Artifact | Full audit trail of AI responses |

---

## 🚀 How to Run
1. **Clone the Repo:**
   ```bash
   git clone [https://github.com/YOUR_USERNAME/Enterprise-RAG-MLOps.git](https://github.com/YOUR_USERNAME/Enterprise-RAG-MLOps.git)
