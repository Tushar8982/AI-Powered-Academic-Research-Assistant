# Academic Research Search with Gemini

A retrieval-augmented search project that extracts text from research papers, creates Gemini embeddings, indexes the document chunks with FAISS, and returns relevant passages for a user query.

## Project Structure

```text
.
|-- RAG_Academic_Research_Search_Gemini.ipynb  # Main documented workflow
|-- requirements.txt                           # Python dependencies
|-- papers/                                    # Research PDFs
|-- .env                                      # Local configuration and API key
```

`solution.ipynb` is intentionally excluded from GitHub through `.gitignore`.

## Requirements

- Python 3.10 or newer
- A Google Gemini API key

## Setup

1. Create and activate a virtual environment:

   ```bash
   python -m venv .venv
   ```

   Windows PowerShell:

   ```powershell
   .venv\Scripts\Activate.ps1
   ```

2. Install the dependencies:

   ```bash
   python -m pip install -r requirements.txt
   ```

3. Create a `.env` file in the project root. Add your API key and local settings:

   ```text
   GEMINI_API_KEY=your_api_key_here
   GEMINI_MODEL=gemini-2.5-flash
   EMBEDDING_MODEL=gemini-embedding-001
   VECTOR_DB=faiss
   CHROMA_PERSIST_DIRECTORY=./chroma_db
   CHUNK_SIZE=1000
   CHUNK_OVERLAP=200
   TOP_K=3
   ```

   Never commit `.env` or share your API key.

## Run

Open `RAG_Academic_Research_Search_Gemini.ipynb` in VS Code or Jupyter and run the cells in order. The notebook loads PDFs from `papers/`, generates embeddings, builds a FAISS index, and lets you search the indexed content.

When prompted, enter a research question. Use `exit` to stop the interactive search loop.

## Notes

- Gemini API usage is subject to quota and rate limits.
- Make sure you have permission to distribute any PDFs included in `papers/` before publishing this repository.
- The excluded `solution.ipynb` is a local working file and is not part of the public project.
