# Smart PDF Chatbot

A Streamlit retrieval-augmented generation demo for asking questions about a PDF. It extracts text, creates chunks and embeddings, retrieves passages with FAISS, and uses an Ollama model to draft an answer.

## Pipeline

~~~text
PDF → extraction → chunks → embeddings → FAISS retrieval
    → selected context → Ollama response
~~~

The current implementation uses 700-character chunks with 100-character overlap, sentence-transformers/all-MiniLM-L6-v2 embeddings, MMR retrieval with up to three passages, and the configured Ollama model (mistral in the current app). It retains a short recent chat history.

## Run locally

~~~bash
git clone https://github.com/Ravi506051/RAG-based-PDF-chatbot-main.git
cd RAG-based-PDF-chatbot-main
python -m venv .venv
# Windows: .venv\Scripts\activate
pip install -r requirements.txt
~~~

Install and start Ollama, pull the model configured in app.py, then run:

~~~bash
streamlit run app.py
~~~

The repository includes economics.pdf as a sample document.

## Quality and privacy

Answers depend on extracted text and retrieved passages. Verify important answers against the source PDF. Scanned documents, tables, multi-column layouts, and questions not answered in the PDF may produce incomplete responses. Do not upload confidential files to an environment you do not trust.

## Maintainer

Ravi Kumar Rao · [GitHub](https://github.com/Ravi506051)
