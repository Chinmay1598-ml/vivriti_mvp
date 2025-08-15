# 🧠 Vivṛti – A Local-First RAG-based Corporate Policy Assistant

Vivṛti is a lightweight, free-tier **Retrieval-Augmented Generation (RAG)** system designed to analyze and answer questions from corporate policy documents (PDFs, DOCXs, XLSXs). Built entirely in **Google Colab**, it uses **MiniLM for embeddings**, **ChromaDB as a vector store**, and **Phi-2 / HuggingFace LLMs** for answering user questions — all **without any paid cloud services**.

---

## 🚀 Demo

> 💬 “What is the upskilling policy for engineers?”

✅ Context-retrieved answer:  
_"Engineers are entitled to enroll in approved training programs and claim reimbursement up to ₹25,000 per annum."_  
📚 Sources: `upskilling_policy.docx`, `hr_policy_2.pdf`

---

## 📂 Project Structure

### vivriti_mvp/

#### ├── notebooks/

│ └── vivriti_main.ipynb # Full pipeline (upload → RAG → LLM)

#### ├── data/

│ └── uploads/ # Raw PDFs, DOCXs, XLSXs

├── chroma_db/ # Local vector store

├── chunk_metadata.csv # Cleaned + chunked text from docs

├── qa_log.csv # Query logs + answers + source docs

├── tagged_chunks.csv # Career-related clause tags (promotion, raise, etc.)

├── parse_failures.csv # Logs files with no extractable text

├── requirements.txt

└── README.md



---

## ⚙️ Tech Stack

| Layer        | Tool/Library            |
|--------------|--------------------------|
| 💬 LLM       | `microsoft/phi-2` (HuggingFace Transformers) |
| 📚 Embeddings| `sentence-transformers` (`MiniLM-L6-v2`) |
| 🔍 Vector DB | `ChromaDB` (duckdb+parquet) |
| 📄 Parsing   | `PyPDF2`, `python-docx`, `openpyxl` |
| 📈 NLP Tags  | Regex-based career pattern extraction |
| 📊 Analytics | Pandas, NetworkX, Matplotlib (optional) |
| 🧪 Platform  | Google Colab (with optional local fallback) |

---

## ✅ Features

- 📤 Upload policy files (PDF, DOCX, XLSX)
- 🧹 Parse, clean, and chunk document text
- 🧠 Embed with MiniLM and store in ChromaDB
- 🔁 Retrieve relevant content for any query
- 🤖 Use Phi-2 or HuggingFace LLMs for natural language answers
- 🏷️ Career impact insights (promotion, raise, training detection)
- 🧾 Logs all Q&A with source documents
- 💾 Free-tier, local-first design — no cloud hosting required

---

## 🧠 Example Use Cases

- Ask: “What is the termination notice period?”
- Discover: “Is there a policy for L&D reimbursements?”
- Analyze: “Does the policy mention appraisals or promotions?”

---

## 📥 How to Run

### Option 1: Google Colab (Recommended)
1. Open `notebooks/vivriti_main.ipynb` in Colab
2. Upload your policy files to `data/uploads/`
3. Run all cells step-by-step

### Option 2: Locally
1. Install Python 3.10+ and `requirements.txt`
2. Run code in Jupyter or convert to FastAPI backend
3. Host with local LLM using `llama-cpp-python`

---

## 🛡️ Limitations

- No OCR support (image-only PDFs will fail gracefully)
- English-language documents only
- Designed for inference, not document editing

---

## 📣 Author

👤 **Chinmay Deshpande**  
---


## 🤝 Contributions Welcome

Want to add OCR? React frontend? FastAPI version? Fork and PR!

---

## 📜 License

MIT License — use freely with attribution.
