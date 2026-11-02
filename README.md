# Smart PDF Chatbot — Retrieval-Augmented Generation

A document-question-answering application that lets users upload PDF files and ask questions about their contents. The project uses a retrieval-augmented generation (RAG) workflow to ground responses in retrieved document passages.

## Features
- PDF upload and text extraction
- Text chunking and embedding generation
- Vector similarity search with FAISS
- Context-aware question answering
- Local language-model inference through Ollama
- Streamlit-based user interface

## Technology
Python · Streamlit · LangChain · FAISS · Hugging Face Embeddings · Sentence Transformers · Ollama · PDF Parsing

## Architecture
```text
PDF upload → Text extraction → Chunking → Embeddings
           → FAISS retrieval → Relevant context
           → Local LLM → Answer
```

## Setup
```bash
git clone https://github.com/Ravi506051/RAG-based-PDF-chatbot-main.git
cd RAG-based-PDF-chatbot-main
python -m venv .venv
# Windows: .venv\\Scripts\\activate
pip install -r requirements.txt
```
Install and start Ollama, then download the model configured by the application. Run the Streamlit entry point documented in the repository.

## Quality and safety
Check whether answers are supported by retrieved passages. Test scanned PDFs, long documents, empty files and questions with no matching context. Do not upload confidential documents to an environment you do not control.

## Future improvements
Add source-page citations, retrieval evaluation, configurable chunking and document-level access controls.

## Maintainer
**Ravi Kumar Rao** · [GitHub](https://github.com/Ravi506051)
