
# 📱 WhatsApp-Driven Google Drive Assistant

Easily manage your Google Drive via WhatsApp using simple text-based commands!  
This assistant integrates **n8n**, **Twilio WhatsApp API**, **Google Drive API**, and **OpenAI GPT** to help you:

- 📂 List, delete, and move files
- 🧠 Summarize documents (PDF, TXT, DOCX)
- 💬 Interact in real time through WhatsApp

All of this—without opening Google Drive!

---

## 🚀 Features

- `LIST /FolderName` — Displays all files within the specified folder  
- `DELETE /FolderName/FileName` — Removes the specified file  
- `MOVE /FolderName/FileName /DestinationFolder` — Relocates a file to another folder  
- `SUMMARY /FolderName` — Generates summaries of documents within a folder  

---

## 🛠 Tech Stack

- **Flask (Python)** — Manages webhooks and API logic  
- **n8n** — Automates workflows (importable JSON provided)  
- **Twilio WhatsApp API** — Enables WhatsApp-based interaction  
- **Google Drive API** — Supports all file operations  
- **OpenAI GPT** — Provides AI-powered document summaries  
- **ngrok** — Tunnels your local server for public access  

---

## 📁 Project Structure

```
whatsapp-driven-google-assistant/
│
├── app.py              # Main Flask application
├── drive_utils.py      # Google Drive helper functions
├── ai_utils.py         # AI summarization logic
├── parser.py           # Parses incoming WhatsApp commands
├── log.py              # Logger setup
├── log_utils.py        # Logging utilities
├── requirements.txt    # Python dependencies
├── workflow.json       # n8n workflow config
├── .env.example        # Example environment config
├── .gitignore          # Files to be excluded from version control
└── README.md           # Project documentation
```

---

## ⚡ Setup Guide

### 1. Clone the Repository

```bash
git clone https://github.com/<your-username>/whatsapp-driven-google-assistant.git
cd whatsapp-driven-google-assistant
```

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

### 3. Configure Environment

- Create a `.env` file based on `.env.example`  
- Add your Google Service Account JSON filename:

```env
GOOGLE_CLIENT_SECRETS_FILE=whatsapp-drive-assistant-xxxx.json
```

📌 Ensure the JSON file is in the root directory, and **never** commit it.

### 4. Start the Flask Server

```bash
python app.py
```

Visit [http://127.0.0.1:5000](http://127.0.0.1:5000)  
You should see: **"WhatsApp Google Drive Assistant is running!"**

### 5. Expose Locally with ngrok

```bash
ngrok http 5000
```

Copy the generated public URL (e.g., `https://abcd1234.ngrok-free.app`)

### 6. Set Up Twilio WhatsApp Sandbox

- Visit **Twilio Console → WhatsApp Sandbox**  
- Set **When a message comes in** to:

```
https://abcd1234.ngrok-free.app/webhook
```

Save your settings.

### 7. Try Sample Commands

Join the sandbox by sending `join <code>` to `+14155238886`. Then try:

```bash
LIST /ProjectX
SUMMARY /ProjectX
MOVE /ProjectX/report.pdf /Archive
DELETE /ProjectX/notes.txt
```

---

## 🎯 Use Cases

- **Students** — Instantly organize and access assignments  
- **Teams** — Manage shared folders remotely  
- **Developers** — Use as a foundation for chat-based cloud automation  

---

## 🔒 Security

- Secrets and credentials are excluded via `.gitignore`  
- Service account JSON must remain untracked  
- A safe `.env.example` is included for environment setup

---

## 🌱 Future Enhancements

- Support for natural language commands (e.g., “Move the report to Archive”)  
- Ability to upload files via WhatsApp  
- Multi-user support using Google OAuth  
- Enhanced AI summarization models and controls  

---

## 🤝 Contributing

We welcome contributions!  
Simply fork the repo, create a feature branch, and submit a pull request.

---

## 📜 License

Licensed under the **MIT License** — free to use, modify, and distribute.

---

## ⭐ Show Your Support

If you find this project helpful, give it a ⭐ on GitHub to show your appreciation and support future improvements!
