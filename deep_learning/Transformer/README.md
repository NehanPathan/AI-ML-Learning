# Transformers & Sequence-to-Sequence Modeling

Fine-tuning modern Transformer models for NLP tasks using **Hugging Face Transformers**, **PyTorch**, and the **SAMSum** dialogue dataset.

---

## 📂 Directory Contents

```
Transformer/
├── text_summarizer.ipynb            # End-to-end notebook fine-tuning T5 on dialogue summarization
├── samsum-train.csv                 # SAMSum training split (dialogues and human summaries)
├── samsum-validation.csv            # SAMSum validation split for intermediate evaluation
├── samsum-test.csv                  # SAMSum test split for final ROUGE score metrics
├── saved_summary_model/             # Saved fine-tuned T5 weights, config, and tokenizer
├── results/                         # Evaluation checkpoints and training loss logs
└── Mini_Proj_Text_Summarizer/       # FastAPI interactive web application for real-time summarization
```

---

## 🏗️ Transformer Architecture Highlights

The Transformer architecture (Vaswani et al.) replaces recurrence with **Self-Attention**:

$$\text{Attention}(Q, K, V) = \text{softmax}\left(\frac{QK^T}{\sqrt{d_k}}\right)V$$

- **Encoder-Decoder (Seq2Seq)**:
  - Models like **T5 (Text-to-Text Transfer Transformer)** and **BART** encode input context and autoregressively generate output sequences.
- **Prefix Conditioning**:
  - T5 uses task-specific prefixes, e.g., `"summarize: " + dialogue`.

---

## 📊 Dataset: SAMSum Dialogue Corpus

The **SAMSum** dataset contains realistic messenger conversations and corresponding human-written summaries:

| Column | Description |
| :--- | :--- |
| `id` | Unique sample identifier |
| `dialogue` | Raw multi-turn conversation between speakers |
| `summary` | Concise, third-person summary of key decisions or events |

---

## 🚀 Training Pipeline (`text_summarizer.ipynb`)

1. **Tokenization**:
   - `T5Tokenizer.from_pretrained('t5-small')` with dynamic padding and max token length truncation.
2. **Seq2Seq Trainer**:
   - `Seq2SeqTrainingArguments` with FP16 precision, warmup steps, and evaluation every epoch.
3. **Metric Evaluation**:
   - ROUGE-1, ROUGE-2, and ROUGE-L scores computed on the test set via the `evaluate` library.
4. **Model Export**:
   - Persisting the trained model and tokenizer into `./saved_summary_model/` for deployment.

---

## 🌐 Web App Deployment

For the interactive web application, visit [`Mini_Proj_Text_Summarizer/`](Mini_Proj_Text_Summarizer/README.md).
