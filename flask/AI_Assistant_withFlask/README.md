# AI Assistant Web App with Flask

A full-stack web application powered by **Flask** and **OpenAI API** providing an interactive AI Assistant for question-answering and email summarization.

---

## 📂 Project Structure

```
AI_Assistant_withFlask/
├── main.py              # Flask server, route definitions, and OpenAI API calls
├── templates/
│   └── index.html       # Web user interface template
├── static/              # CSS stylesheets, client JavaScript, and UI assets
└── .gitignore           # Git ignore configuration for virtualenvs and secrets
```

---

## 🌟 Application Features

1. **AI Chat & Q&A (`POST /ask`)**:
   - Takes questions from the user via web form or AJAX.
   - Queries OpenAI models with a persona-guided system prompt (`"Act like a helpful personal assistant"`).
   - Returns JSON responses for seamless UI updates.
2. **Email Summarization (`POST /summarize`)**:
   - Ingests lengthy email threads or text bodies.
   - Produces clear 2-3 sentence summaries focusing on action items and core messages.

---

## 🚀 How to Run Locally

### 1. Install Requirements
```bash
pip install flask python-dotenv openai
```

### 2. Configure Environment
Create a `.env` file in this directory:
```env
OPENAI_API_KEY=your_openai_api_key_here
```

### 3. Launch Flask Server
```bash
python main.py
```
Open your browser and navigate to:
```
http://127.0.0.1:5000/
```
