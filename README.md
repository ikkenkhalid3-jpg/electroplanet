# Electroplanet Learning Assistant

A simple beginner-friendly AI chatbot built with **Python**, **Streamlit**, and the **Groq API**. It answers questions using facts in `Electroplanet-knowledge.json` and remembers the conversation while the current Streamlit session is active.

> This is an unofficial educational prototype, not affiliated with Electroplanet. The JSON file is a static research snapshot, not live stock, pricing, or service information.

## Project files

```text
electroplanet-chatbot/
├── app.py
├── .env
├── .gitignore
├── requirements.txt
├── README.md
└── Electroplanet-knowledge.json
```

Keep `Electroplanet-knowledge.json` in the same folder as `app.py`.

## 1. Requirements

- Python 3.10 or newer
- Internet connection
- A Groq API key from [Groq Console](https://console.groq.com/keys)

## 2. Create and activate a virtual environment

Open a terminal in the project folder.

**Windows (PowerShell):**

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

**macOS / Linux:**

```bash
python3 -m venv .venv
source .venv/bin/activate
```

## 3. Install libraries

```bash
pip install -r requirements.txt
```

## 4. Configure the API key

Open `.env` and replace the placeholder with your own Groq API key:

```dotenv
GROQ_API_KEY=your_groq_api_key_here
```

The placeholder is not a working key. Keep your real key private, do not paste it into `app.py`, and do not commit `.env` to Git. The `.gitignore` file excludes it.

## 5. Run the chatbot

```bash
streamlit run app.py
```

Streamlit will show a local URL in the terminal, usually `http://localhost:8501`. Open it in your browser.

## Features

- Chat interface using `st.chat_message()` and `st.chat_input()`
- Session-only conversation memory using `st.session_state`
- Clear-conversation button
- Answers grounded in the supplied JSON knowledge file
- Friendly handling for missing API keys, missing/invalid JSON, and API errors
- Groq model: `openai/gpt-oss-20b`

Model availability and free-tier limits can change. If Groq reports that the model is unavailable to your account, select a currently available model from the [Groq Console documentation](https://console.groq.com/docs/models) and update the `model=` value in `app.py`.

## Notes

- Chat history is held in Streamlit session state; it is not saved to a database and may disappear when the session resets.
- The knowledge JSON was researched on **2026-10-18**. Prices, policies, service details, and availability should be confirmed through the official links in the knowledge file.
- The app does not check live stock or perform purchases, bookings, refunds, or other transactions.
