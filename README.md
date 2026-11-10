# Smart PDF Chatbot — Retrieval-Augmented Generation

A document question-answering application that allows users to upload PDF files and ask questions about their contents. The RAG workflow retrieves relevant document passages and supplies them as context for answer generation.

## Features
- PDF upload and text extraction.
- Text chunking and embedding generation.
- Similarity search with FAISS.
- Context-aware question answering.
- Local language-model inference through Ollama.
- Streamlit user interface.

## Architecture
```text
PDF → Text Extraction → Chunking → Embeddings
    → FAISS Search → Retrieved Context
    → Ollama LLM → Answer
```

## Technology
Python · Streamlit · LangChain · FAISS · Hugging Face Embeddings · Sentence Transformers · Ollama

## Setup
```bash
git clone https://github.com/Ravi506051/RAG-based-PDF-chatbot-main.git
cd RAG-based-PDF-chatbot-main
python -m venv .venv
# Windows: .venv\Scripts\activate
pip install -r requirements.txt
```
Install Ollama, download the model configured by the application, and launch the Streamlit entry point documented in the repository.

## Quality Checks
Test with short and long PDFs, scanned documents, empty files, and questions with no supporting passage. Review retrieved chunks to verify that generated answers are grounded in the source document. Avoid uploading confidential documents to untrusted environments.

## Future Improvements
- Display source-page references with answers.
- Evaluate retrieval precision and answer faithfulness.
- Make chunk size and overlap configurable.
- Add document-level access controls.

## Maintainer
**Ravi Kumar Rao** · [GitHub](https://github.com/Ravi506051)

## Retrieval Quality and Grounding

- Evaluate whether retrieved chunks actually contain evidence relevant to each question.
- Tune chunk size, overlap, and retrieval count using representative documents and queries.
- Keep source passages available so users can verify generated answers.
- Test scanned PDFs, tables, long documents, and questions whose answers are absent from the source; the system should communicate uncertainty.
