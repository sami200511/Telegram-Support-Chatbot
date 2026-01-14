# AI Customer Support Telegram Bot 🤖

A professional Customer Support Telegram bot powered by **Google Gemini AI**. This bot acts as an intelligent assistant for a SaaS/Data Analysis website, handling inquiries about pricing, services, and technical support while maintaining a strict professional persona.

## 🚀 Features

* **AI-Powered Responses:** Uses Google's `genai` SDK (Gemini Models) to generate natural, context-aware answers.
* **Strict Persona:** Configured to act solely as a customer support agent. It refuses off-topic questions (e.g., general knowledge, personal questions).
* **Service Knowledge Base:** Pre-trained (via system instructions) on specific plans, pricing, and services.
* **Human Escalation:** Automatically directs complex issues to a human support email when the AI cannot help.
* **Error Handling:** graceful error management and logging.

## 🛠️ Prerequisites

* Python 3.8 or higher
* A Telegram Bot Token (from [@BotFather](https://t.me/BotFather))
* A Google Gemini API Key (from [Google AI Studio](https://aistudio.google.com/))

## 📦 Installation

1.  **Clone the repository** (or create your project folder):
    ```bash
    mkdir support-bot
    cd support-bot
    ```

2.  **Install the required Python libraries:**
    You need the Google GenAI SDK and the Telegram Bot wrapper.
    ```bash
    pip install google-genai python-telegram-bot
    ```

## ⚙️ Configuration

1.  Open the script file (e.g., `T_BOT.py`).
2.  Replace the placeholder credentials with your actual keys:

```python
# In T_BOT.py
TELEGRAM_TOKEN = "YOUR_TELEGRAM_BOT_TOKEN"
GEMINI_API_KEY = "YOUR_GOOGLE_GEMINI_API_KEY"
```

## ⚙️ Customization

The bot's "brain" is the `SYSTEM_INSTRUCTION` variable in `T_BOT.py`. You can edit this string to tailor the bot to your specific needs:

* **Business Logic:** Update the `Website Services` and `Pricing` sections to reflect your actual product catalog.
* **Support Contact:** Change the email address under `Human Support Escalation` to your real support email.
* **Persona:** Modify the `Tone and Communication Style` section to make the bot sound more formal, casual, or friendly.

## ▶️ Usage

1.  **Start the bot:**
    ```bash
    python T_BOT.py
    ```
2.  **Verify:**
    You should see the message: `INFO:root:Bot is running...` in your terminal.
3.  **Interact:**
    Open your bot in Telegram and send the command `/start` to begin the conversation.

## 🧠 Model Configuration

By default, this bot is configured to use `gemini-3-flash-preview`.

If you encounter API errors regarding model availability, locate the `client.models.generate_content` call in the code and switch the model to a stable version:

```python
# Change "gemini-3-flash-preview" to one of these:
model="gemini-1.5-flash"
# OR
model="gemini-2.0-flash-exp"
```
