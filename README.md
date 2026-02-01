# 📘 Explainable PDF Question Answering (RAG App)

An **Explainable Retrieval-Augmented Generation (RAG)** system that allows users to upload a PDF, ask questions about its content, and receive:
- 📖 A grounded answer  
- 🧠 An explanation of *why* specific context was used  
- 📄 Source pages with relevance scores  

Built using **Gradio, LangChain, ChromaDB, and Hugging Face models**.

---

## 🚀 Features

- 📂 Upload and index any PDF
- 🔍 Semantic search using embeddings (MiniLM)
- 🤖 Question answering using FLAN-T5
- 🧠 Explainability layer: *why this answer?*
- 📄 Source attribution with relevance scores
- 💻 Runs fully on CPU (Colab / low-resource friendly)

---

## 🧠 Architecture (High Level)

1. **PDF Loader**  
   Uses `PyPDFLoader` to extract text from PDFs.

2. **Text Chunking**  
   Splits text into overlapping chunks using `RecursiveCharacterTextSplitter`.

3. **Embeddings**  
   - Model: `sentence-transformers/all-MiniLM-L6-v2`
   - Normalized embeddings for accurate similarity scoring.

4. **Vector Store**  
   - `ChromaDB` for fast semantic retrieval
   - Persistent storage

5. **LLM**  
   - `go
