# 🤖 Customer Care Backend

A Django REST API backend for an AI-powered chatbot that supports multiple models:
- **Google Gemini**
- **OpenRouter**
- **Groq**
- **Ollama (local models)**

The project uses **Django REST Framework (DRF)** to expose an endpoint `/chat/` where you can send user messages and get AI responses.

---

## 🚀 Features
- REST API for chatting with multiple AI models
- Supports **Gemini, OpenRouter, Groq, Ollama**
- Stores chat history in a database
- Modular and extensible design
- `.env` based API key configuration

---

## 📂 Project Structure
```

├── chatbot_app/             # Django app
│   ├── models.py            # ChatMessage model
│   ├── views.py             # API logic
│   ├── urls.py              # Routes for API
├── requirements.txt         # Dependencies
├── manage.py                # Django management script
└── README.md                # Documentation

````

---

## ⚡ Setup & Installation

### 1️⃣ Clone the repository
```bash
git clone https://github.com/your-username/django-ai-chatbot.git
cd django-ai-chatbot
````

### 2️⃣ Create & activate a virtual environment

```bash
python -m venv venv
source venv/bin/activate   # On macOS/Linux
venv\Scripts\activate      # On Windows
```

### 3️⃣ Install dependencies

```bash
pip install -r requirements.txt
```

### 4️⃣ Configure environment variables

Create a `.env` file in the project root and add:

```ini
# Gemini
GEMINI_API_KEY=your_gemini_api_key

# OpenRouter
OPENROUTER_API_KEY=your_openrouter_api_key
OPENROUTER_MODEL=openrouter/model-name

# Groq
GROQ_API_KEY=your_groq_api_key
GROQ_MODEL=groq/model-name

# Ollama (local)
OLLAMA_MODEL=llama2
```

### 5️⃣ Run migrations

```bash
python manage.py migrate
```

### 6️⃣ Start the server

```bash
python manage.py runserver
```

---

## 🔑 API Endpoints

### 🏠 Root

```http
GET /
```

Returns a welcome message.

### 💬 Chat

```http
POST /chat/
Content-Type: application/json

{
  "message": "Hello AI!",
  "model": "gemini"   # options: gemini | openrouter | groq | ollama
}
```

#### ✅ Example Response

```json
{
  "reply": "Hello! How can I assist you today?"
}
```

---

## 🗄 Database

All chat messages are stored in the `ChatMessage` model with:

* `sender` (user/ai)
* `message`
* `timestamp`

---

## 🛠 Tech Stack

* **Python 3.10+**
* **Django 5+**
* **Django REST Framework**
* **Google Generative AI (Gemini)**
* **OpenRouter**
* **Groq SDK**
* **Ollama (for local models)**

---

## 📜 License

This project is licensed under the **MIT License**.

---

✨ Built with Django & DRF for AI-powered chat

