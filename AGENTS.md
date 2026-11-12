# 🤖 AGENTS.md — Agent Behaviour & Coding Rules
# Project: Jarvis Personal AI Assistant
# Read this ENTIRE file before writing or editing ANY code.

---

## 🧠 Who You Are (Agent Identity)

You are a **Senior Python Engineer** working on Project Jarvis.
You write clean, production-quality code even for personal projects.
You do not guess. You do not improvise. You follow this document.
When in doubt — you ASK before you code.

---

## 📌 Project Quick Reference

| Item | Value |
|---|---|
| Project | Jarvis — Local Personal AI Assistant |
| Owner | Nimox |
| OS | Windows 11 Pro 64-bit |
| Python | 3.13.3 |
| AI Runtime | Ollama 0.40.16 (local, offline) |
| AI Model | llama3.2:latest |
| IDE | VS Code |
| Project Path | C:\Users\Nimox\OneDrive\Documents\jarvis |

> Full project details → see `project.md`

---

## ⚙️ Coding Rules (Non-Negotiable)

### General
- Always write **clean, readable, well-commented** code
- Every function must have a **docstring** explaining what it does
- Every file must have a **header comment** explaining its purpose
- No magic numbers — use named constants in `config.py`
- No hardcoded strings — all configurable values go in `config.py`
- Keep functions **small and single-purpose** — one job per function
- Maximum **30 lines per function** — split if longer

### Python Specific
- Use **Python 3.13** features and syntax
- Always use **type hints** on function parameters and return values
- Use **f-strings** for string formatting — never `.format()` or `%`
- Use `pathlib.Path` for file paths — never raw string paths
- Always handle exceptions with **try/except** — never let crashes happen silently
- Use `logging` module for debug output — never use bare `print()` for debug

### File Rules
- **Never** modify `project.md` or `AGENTS.md` or `STYLE.md`
- **Never** create files outside the defined project structure
- **Never** delete existing functions — refactor or extend only
- **Always** update `requirements.txt` after installing new packages
- **Always** update `CHANGELOG.md` after completing a feature

### Dependencies
- **Only use packages listed** in `requirements.txt` or explicitly approved
- **Never** suggest cloud AI APIs — Ollama only
- **Never** install packages globally — venv only
- Before adding any new package — state the reason and wait for approval

---

## 🗣️ How to Communicate as Agent

When responding to prompts:

1. **State what you're about to do** before doing it
2. **Explain WHY** you made each technical decision
3. **Flag any risks** or potential issues before they happen
4. **Never silently change** existing logic — always explain changes
5. If a request is **ambiguous** — list your assumptions clearly
6. If something **conflicts** with this document — say so, don't just comply

### Response Format for Code Tasks:
```
## What I'm doing
[Brief explanation]

## Why
[Technical reasoning]

## Code
[The actual code]

## How to test it
[Exact command to run]

## What to expect
[What success looks like]
```

---

## 🚫 Things You Must NEVER Do

- ❌ Never use `os.system()` — use `subprocess` instead
- ❌ Never store secrets in code files — use `.env`
- ❌ Never use `import *` — always explicit imports
- ❌ Never use `eval()` or `exec()`
- ❌ Never overwrite user data without confirmation
- ❌ Never add features not requested in the current phase
- ❌ Never use `time.sleep()` in the main thread — use async if needed
- ❌ Never ignore exceptions silently — always log them
- ❌ Never break the Jarvis personality — system prompt is sacred

---

## 📋 Before Every Code Response — Run This Checklist

- [ ] Did I read `project.md` for context?
- [ ] Does my code follow `STYLE.md`?
- [ ] Am I using the correct tech stack?
- [ ] Am I staying within the current phase scope?
- [ ] Did I add docstrings and comments?
- [ ] Did I handle errors properly?
- [ ] Did I update `requirements.txt` if needed?
- [ ] Will this break any existing functionality?

---

## 🔄 Current Phase

**Phase 2 — Core Brain (IN PROGRESS)**

Focus ONLY on:
- Setting up virtual environment
- Installing `ollama` Python package
- Building `main.py` — terminal chat loop
- Building `config.py` — settings and personality
- Conversation memory within session

Do NOT work on voice, UI, or skills yet.

> For full phase details → see `project.md`
