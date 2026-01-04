# RAG-based PDF Question Answering Bot

## Project Overview
This project is a **PDF-based QA Bot** built using **LangChain**, **IBM Watsonx LLM & Embeddings**, and **Chroma** for vector storage. The bot uses a **Retrieval-Augmented Generation (RAG)** pipeline to answer questions based on the content of uploaded PDF documents.

Users can upload PDFs and ask queries, and the bot will return context-aware answers by retrieving relevant document chunks and generating a response using IBM Watsonx LLM.

---

## Features
- Upload PDF files as input
- Automatic document splitting into chunks
- Vector database creation using **Chroma**
- Embeddings generated with **IBM Watsonx slate-30m**
- Query answering using **RetrievalQA** pipeline
- Interactive interface using **Gradio**

---

## Technologies Used
- Python
- [LangChain](https://www.langchain.com/)
- [IBM Watsonx LLM & Embeddings](https://www.ibm.com/watsonx)
- [Chroma](https://www.trychroma.com/)
- Gradio for web interface
- HuggingFace Hub integration

---

## Installation

1. Clone the repository:

```bash
   git clone https://github.com/amarkumar55/RAG-based-PDF-Question-Answering-Bot.git
   cd RAG-based-PDF-Question-Answering-Bot
```

Create a virtual environment and activate it:

    python -m venv venv
    source venv/bin/activate 
    venv\Scripts\activate    

Install dependencies:

    pip install -r requirements.txt
    Update your IBM Watsonx credentials in the app.py (or use environment variables).

Usage

    Run the Gradio app:
    
    python app.py
    
    Open the browser at:
    
    http://127.0.0.1:7860

    Upload a PDF and ask your questions in the input box. The bot will return answers using the content from the PDF.

Project Structure

```text
RAG-based-PDF-Question-Answering-Bot/
│
├── app.py
├── requirements.txt
├── README.md

```
### Author

### Amar Kumar
### AI / Machine Learning Enthusiast

---
