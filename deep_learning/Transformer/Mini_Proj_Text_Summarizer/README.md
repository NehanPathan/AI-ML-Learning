# Mini Project: Text Summarizer Web App

A production-ready **FastAPI** web application serving a fine-tuned **T5 Transformer** model for real-time dialogue and text summarization.

---

## 📂 Project Structure

```
Mini_Proj_Text_Summarizer/
├── app.py                   # FastAPI backend server with T5 inference pipeline
├── index.html               # Frontend HTML/CSS interface for interactive user input
└── saved_summary_model/     # Fine-tuned model checkpoint and tokenizer files
```

---

## 🌟 Features

- **Fast & Responsive**: Built on top of asynchronous FastAPI.
- **Preprocessing Pipeline**: Cleans carriage returns, excessive whitespaces, and stray HTML tags before inference.
- **Transformer Generation**: Uses beam search or greedy decoding via PyTorch to generate concise summaries.
- **Hardware Agnostic**: Automatically detects and leverages Apple Silicon MPS, NVIDIA CUDA, or CPU fallback.

---

## 🚀 Getting Started

### 1. Install Dependencies
```bash
pip install fastapi uvicorn torch transformers jinja2 pydantic
```

### 2. Start the Server
From this directory:
```bash
uvicorn app:app --reload --host 127.0.0.1 --port 8000
```

### 3. Open the Interface
Navigate in your browser to:
```
http://127.0.0.1:8000
```
Enter any multi-speaker conversation or long text, and click **Summarize** to get an instant summary!

---

## 🔌 API Endpoint

- **Endpoint**: `POST /summarize`
- **Request Body**:
  ```json
  {
    "dialogue": "Alice: Are we still meeting at 5pm? Bob: Yes, see you at the cafe. Alice: Great, bringing the laptop."
  }
  ```
- **Response**:
  ```json
  {
    "summary": "Alice and Bob confirm their meeting at 5pm at the cafe."
  }
  ```
