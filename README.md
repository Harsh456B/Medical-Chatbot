# Medical-Chatbot

Medical-Chatbot is a Streamlit-based medical assistant that provides concise, user-friendly answers for health-related questions. The app is built to run in a browser and offers a simple conversational interface with a medical-focused assistant.

## Project Overview

This project is designed as a demonstration of a medical chatbot interface using Streamlit. It uses a Groq-powered fallback language model for responses and is currently configured to disable RAG support for compatibility with Python 3.14.

### What it does
- Presents a web-based chat UI for users to ask medical or health-related questions.
- Sends user input to a lightweight Groq LLM via the `langchain_groq` package.
- Returns concise answers limited to a few sentences.
- Suggests consulting a medical professional when uncertain.
- Stores chat history in the Streamlit session state so the conversation persists on the page.

### Key characteristics
- **Frontend:** Streamlit app with custom CSS to match the intended chat UI.
- **LLM integration:** Groq ChatGroq fallback model.
- **RAG status:** RAG pipeline is intentionally disabled in `app.py` for Python 3.14 compatibility.
- **Deployment-ready:** Can be launched locally with Streamlit and is suitable for deployment on platforms that support Streamlit apps.

## Features

- Clean Streamlit chat interface
- Persistent chat history per browser session
- Groq LLM fallback for fast inference
- Custom medical prompt instructions
- Easy configuration via `.env`

## Built With

- Python 3.12+ (compatible with Python 3.14 in this repository)
- Streamlit
- LangChain
- Groq
- Python Dotenv

## Prerequisites

- Python 3.12 or newer
- A virtual environment is strongly recommended
- A valid `GROQ_API_KEY` stored in a `.env` file

## Installation

From the project root:

```bash
python -m pip install -r requirements.txt
```

## Configuration

Create a `.env` file in the project root with the following values:

```env
GROQ_API_KEY=your_groq_api_key
```

The repository also includes placeholders for `PINECONE_API_KEY` and other optional values, but the current application execution path does not use Pinecone or RAG.

## Running the App

From the project root, run:

```bash
python -m streamlit run app.py
```

Then open the displayed URL in your browser, usually `http://localhost:8501`.

## File Structure

- `app.py` — Streamlit application entry point and UI logic.
- `requirements.txt` — Python package dependencies.
- `src/` — Supporting Python source modules.
- `config/` — Project configuration files.
- `static/`, `templates/` — UI assets and templates.

## Notes

- The current app implementation uses a fallback LLM rather than a full RAG pipeline.
- The app is configured to use `GROQ_API_KEY` and will raise an error if it is missing.
- The outdated `data/Medical_book.pdf` file has been removed from the repository.

## Contributions

Contributions are welcome. If you want to extend this project, consider:

- Restoring and enabling RAG support with Pinecone or another vector store.
- Adding more medical safety prompts and response validation.
- Improving deployment documentation and environment setup.

## License

This repository does not specify a license in the README. Add one if you want to share the project publicly under a clear license.
