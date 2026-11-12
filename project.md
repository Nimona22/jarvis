# 🤖 Project Jarvis — Project Context Document

> **Read this entire file before writing, editing, or suggesting any code.**
> This document is the single source of truth for the Jarvis project.

---

## 📌 Project Overview

**Project Name:** Jarvis  
**Type:** Personal AI Assistant (Desktop, Local)  
**Owner:** Nimox  
**Platform:** Windows 11 Pro (HP EliteBook 840 G6)  
**Status:** In Development — Phase 2 (Core Brain)

Jarvis is a fully local, voice-enabled personal AI assistant that runs on the owner's laptop. It requires no internet connection to function. It is inspired by J.A.R.V.I.S. from Iron Man — professional, smart, slightly witty, and always addresses the user as "Sir."

---

## 🎯 Goals

- Build a personal AI assistant that works 100% offline
- Runs entirely on local hardware — no paid API calls
- Voice input and voice output (speak to it, it speaks back)
- Responds with a Jarvis-like personality
- Expandable with skills/features over time
- Zero monthly cost

---

## 🧰 Tech Stack

| Layer | Tool | Version | Notes |
|---|---|---|---|
| Language | Python | 3.13.3 | Installed |
| Package manager | pip | 26.0.1 | Installed |
| Local AI runtime | Ollama | 0.40.16 | Installed |
| AI Model | Llama 3.2 | latest (2GB) | Downloaded |
| Voice Input | SpeechRecognition | TBD | Phase 3 |
| Voice Output | pyttsx3 | TBD | Phase 3 |
| IDE | VS Code | Latest | Windows |
| Vibe Coding Agent | Gemini (Google Pro) | Latest | Used for code generation |

---

## 📁 Project Structure

```
jarvis/
├── venv/                  ← Python virtual environment (never edit)
├── main.py                ← Entry point — runs Jarvis
├── config.py              ← Settings, constants, personality prompt
├── skills/                ← Individual skill modules (Phase 4)
│   ├── __init__.py
│   ├── open_app.py
│   ├── weather.py
│   └── reminder.py
├── memory/                ← Conversation history (Phase 2)
│   └── history.json
├── requirements.txt       ← All installed packages
├── .gitignore             ← venv, .env, __pycache__ ignored
└── project.md             ← This file
```

---

## 🤖 Jarvis Personality

Jarvis must always follow this personality:

- Addresses the user as **"Sir"** at all times
- Tone: **Professional, calm, intelligent, slightly witty**
- Never says "I am just an AI" or similar disclaimers
- Keeps responses **concise and useful** — no filler
- Starts every session with: **"Good [morning/afternoon/evening], Sir. Jarvis is online. How may I assist you?"**
- Never breaks character

**System Prompt (always include this in every AI call):**
```
You are Jarvis, a highly intelligent personal AI assistant. You are professional, calm, 
efficient, and slightly witty. You always address the user as "Sir". You never say you 
are just an AI or refuse reasonable requests. You give concise, accurate, and helpful 
responses. You are loyal only to your owner and always ready to assist.
```

---

## 🗺️ Build Phases

### ✅ Phase 1 — Environment Setup (COMPLETE)
- [x] Python 3.13 installed
- [x] Pip 26 installed
- [x] Ollama 0.40.16 installed
- [x] Llama 3.2 model downloaded (2GB)
- [x] Brain test passed

### 🔄 Phase 2 — Core Brain (IN PROGRESS)
- [ ] Virtual environment created
- [ ] `ollama` Python package installed
- [ ] `main.py` — basic terminal chat loop
- [ ] `config.py` — personality system prompt
- [ ] Conversation memory (remembers within session)

### ⏳ Phase 3 — Voice (Coming Next)
- [ ] Microphone input via `SpeechRecognition`
- [ ] Voice output via `pyttsx3`
- [ ] Wake word detection "Hey Jarvis"

### ⏳ Phase 4 — Smart Skills
- [ ] Open apps by voice command
- [ ] Tell time and date
- [ ] Weather lookup
- [ ] Web search
- [ ] Set reminders

### ⏳ Phase 5 — UI Dashboard
- [ ] Sleek Jarvis-style desktop UI
- [ ] Animated listening indicator
- [ ] Chat history panel

---

## ⚙️ Rules for the Coding Agent

> These rules apply to **every single prompt and code change** in this project.

1. **Always use the tech stack above** — do not suggest alternatives unless asked
2. **Never use OpenAI, Anthropic, or any cloud AI API** — Ollama only
3. **Always use the venv** — never install packages globally
4. **Follow the folder structure above** — do not create files outside it without asking
5. **Never overwrite `project.md`** — this file is read-only reference
6. **Always include the Jarvis system prompt** in every Ollama call
7. **Keep code clean and commented** — explain what each section does
8. **One feature at a time** — do not add features not requested in the current phase
9. **If something is unclear** — ask before guessing
10. **Always use `requirements.txt`** — update it after every new install

---

## 📦 Installed Packages

```
# Updated as packages are installed
ollama          ← Phase 2
speechrecognition ← Phase 3 (not yet)
pyttsx3         ← Phase 3 (not yet)
```

---

## 🔑 Important Notes

- Project folder: `C:\Users\Nimox\OneDrive\Documents\jarvis`
- OS: Windows 11 Pro 64-bit
- No GPU — Ollama runs in CPU mode (5–15 sec response time is normal)
- No API keys needed — everything is local and free
- Do not add cloud dependencies — this must work offline

---

*Last updated: Phase 2 start*  
*CEO: Claude (Anthropic)*  
*Builder: Nimox*  
*Contractor: Gemini (Google)*
