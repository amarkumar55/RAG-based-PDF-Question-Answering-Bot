# 🤖 RAG-Powered PDF Question Answering Bot
### Ask questions from any PDF — powered by LangChain · IBM Watsonx · ChromaDB

![Python](https://img.shields.io/badge/Python-3.8+-blue?style=flat-square&logo=python)
![LangChain](https://img.shields.io/badge/LangChain-latest-teal?style=flat-square)
![IBM Watsonx](https://img.shields.io/badge/IBM_Watsonx-LLM-054ADA?style=flat-square&logo=ibm)
![Gradio](https://img.shields.io/badge/Gradio-UI-orange?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)

> Upload any PDF. Ask questions in plain English. Get precise, context-grounded answers — powered by a production-grade RAG pipeline using IBM Watsonx enterprise LLM.

---

## 🎯 What This Project Does

Most LLMs hallucinate when asked about documents they haven't seen. This bot eliminates that problem by grounding every answer in retrieved content from your actual PDF — no hallucinations, no guesswork.

```
PDF Upload → Chunking → Embedding (Watsonx slate-30m) → ChromaDB
                                                              │
User Query → Semantic Retrieval → RetrievalQA → IBM Watsonx LLM → Answer
```

---

## ✨ Features

- 📄 **Upload any PDF** — no preprocessing required
- ✂️ **Automatic chunking** — splits documents into semantically meaningful segments
- 🔢 **Enterprise embeddings** — IBM Watsonx `slate-30m` for high-quality vector representations
- 🗄️ **ChromaDB vector store** — fast, local semantic search over document chunks
- 🧠 **RetrievalQA pipeline** — LangChain orchestrates retrieval → generation end-to-end
- 🖥️ **Gradio UI** — clean, real-time Q&A interface, zero frontend code

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────┐
│                    INDEXING PIPELINE                     │
│                                                          │
│  PDF File → PyPDF Loader → Text Splitter → Chunks       │
│                                    │                     │
│                          Watsonx Embeddings              │
│                                    │                     │
│                             ChromaDB Store               │
└─────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────┐
│                    QUERY PIPELINE                        │
│                                                          │
│  User Query → Embed Query → Semantic Search (Chroma)    │
│                                    │                     │
│                          Relevant Chunks                 │
│                                    │                     │
│                    IBM Watsonx LLM (RetrievalQA)        │
│                                    │                     │
│                         Grounded Answer                  │
└─────────────────────────────────────────────────────────┘
```

---

## ⚙️ Tech Stack

| Layer | Technology |
|-------|-----------|
| RAG Orchestration | LangChain |
| LLM | IBM Watsonx (enterprise) |
| Embeddings | IBM Watsonx `slate-30m` |
| Vector Store | ChromaDB |
| UI | Gradio |
| Runtime | Python 3.8+ |
| Integration | HuggingFace Hub |

---

## 🚀 Getting Started

### 1. Clone the repository
```bash
git clone https://github.com/amarskdev/RAG-based-PDF-Question-Answering-Bot.git
cd RAG-based-PDF-Question-Answering-Bot
```

### 2. Create and activate virtual environment
```bash
python -m venv venv

# macOS / Linux
source venv/bin/activate

# Windows
venv\Scripts\activate
```

### 3. Install dependencies
```bash
pip install -r requirements.txt
```

### 4. Configure IBM Watsonx credentials
Add your credentials to a `.env` file:
```env
WATSONX_API_KEY=your_api_key_here
WATSONX_PROJECT_ID=your_project_id_here
WATSONX_URL=https://us-south.ml.cloud.ibm.com
```

### 5. Run the app
```bash
python app.py
```

Open your browser at **http://127.0.0.1:7860**, upload a PDF, and start asking questions.

---

## 📁 Project Structure

```
RAG-based-PDF-Question-Answering-Bot/
│
├── app.py                  # Main Gradio app + RAG pipeline
├── requirements.txt        # Python dependencies
├── .env.example            # Credential template (safe to commit)
├── .gitignore              # Excludes .env, venv, __pycache__
└── README.md
```

---

## 🌍 Real-World Use Cases

- 📚 **Research assistance** — query academic papers, reports, whitepapers
- ⚖️ **Legal document review** — extract clauses and obligations from contracts
- 🏢 **Enterprise knowledge base** — make internal docs instantly searchable
- 📋 **Compliance workflows** — audit documents against policies
- 🎓 **Study tool** — ask questions from textbooks and lecture notes

---

## 🔭 Roadmap

- [ ] Multi-PDF support (query across multiple documents)
- [ ] Conversational memory (multi-turn Q&A)
- [ ] Source citation with page numbers
- [ ] REST API via FastAPI + Docker deployment
- [ ] Fine-tuning embeddings on domain-specific corpora

---

*Built with enterprise-grade AI (IBM Watsonx) — not just another OpenAI wrapper.*

---

## 🤝 Connect With Me


<div align="center">

### 👤 About the Author

**Amar Kumar**  
*Senior Backend Engineer · IBM Certified AI Engineer*

[![LinkedIn](https://img.shields.io/badge/LinkedIn-amarskdev-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/amarskdev)
[![GitHub](https://img.shields.io/badge/GitHub-amarskdev-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/amarskdev)
[![Gmail](https://img.shields.io/badge/Gmail-amarsk.dev-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:amarsk.dev@gmail.com)
[![LeetCode](https://img.shields.io/badge/LeetCode-amarskdev-FFA116?style=for-the-badge&logo=leetcode&logoColor=white)](https://leetcode.com/u/amarskdev)
[![Instagram](https://img.shields.io/badge/Instagram-amarsk.dev-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://www.instagram.com/amarsk.dev/)
[![Credly](https://img.shields.io/badge/Credly-Badges-FF6B00?style=for-the-badge&logo=credly&logoColor=white)](https://www.credly.com/users/amarskdev/)

*If you found this project useful, consider giving it a ⭐ — it means a lot!*

</div>

