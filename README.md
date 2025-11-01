# 📩 Email ChatBot (n8n + Telegram + Gmail + Gemini)

The **Email ChatBot** is an AI-powered automation workflow built using **n8n**, **Google Gemini**, **Telegram Bot API**, and **Gmail API**.  
It allows users to **generate and send emails** simply by chatting with a Telegram bot — no manual typing of emails required!

---

## ✨ Features

- ✅ Generate professional email drafts through chat
- ✅ Add automatic signature to every email
- ✅ Preview draft inside Telegram before sending
- ✅ Send the email via Gmail once approved
- ✅ Conversation memory for contextual responses
- ✅ Secure OAuth-based Gmail execution

---

## 🧩 System Architecture

```
Telegram User
      │
      ▼
Telegram Trigger ──► AI Agent (LangChain + Gemini)
                            │
                            ▼
                       Simple Memory
                            │
                            ▼
                  Gmail Tools (Draft / Send)
                            │
                            ▼
                   Back to Telegram Output
```

---

## 🔄 Functional Workflow

1️⃣ User sends a message → Telegram Bot  
2️⃣ n8n workflow triggers  
3️⃣ Message is processed by **AI Agent**  
4️⃣ AI extracts:
- Recipient (`To_Email`)
- Subject
- Email body content

5️⃣ Draft email shared with user in Telegram  
6️⃣ On confirmation → Email is sent via Gmail API  

---

## 🧠 AI Prompt Behavior

The AI understands natural instructions like:

> “Write an email for leave application tomorrow”  
> “Send email to professor about project update”

📝 Every email ends with the signature:

```
Best,

Shreyas
3rd Year CSE - A
```

---

## 🛠️ Technical Components

| Component | Description |
|----------|-------------|
| **n8n** | Orchestrates full workflow |
| **Telegram Trigger** | Captures input from user |
| **Google Gemini Chat Model** | Generates email drafting response |
| **LangChain Agent** | Interprets AI output into fields |
| **Memory Buffer** | Maintains chat context by user ID |
| **Gmail Nodes** | Create draft and send email |
| **Telegram Output** | Shows results to user |

---

## 🚀 Setup Instructions

### ✅ Prerequisites

- n8n instance (Local / Docker / Cloud)
- Telegram Bot Token via **BotFather**
- Gmail OAuth Credentials enabled
- Google Gemini API Key

### 🔧 Install Workflow

1. Import the workflow JSON into n8n  
2. Add credentials:
   - Telegram API
   - Google OAuth2 (Gmail)
   - Google Gemini API
3. Activate workflow
4. Test by messaging your Telegram bot

---

## 🔐 Security Notes

- Gmail access handled securely via n8n encrypted credentials
- Memory separated by user session key → No cross user data leakage
- Draft always shown to user before sending

---

## 📌 Future Enhancements

| Feature | Status |
|--------|--------|
| Buttons for "Send" / "Edit" | 🔜 Planned |
| Multiple signature options | 🔜 Planned |
| Logging emails to Google Sheets | 🔜 Optional add |
| Multi-thread email context | 🔜 Future |

---

## 🧑‍💻 Author

**Shreyas**  
3rd Year CSE - A  
VNRVJIET
