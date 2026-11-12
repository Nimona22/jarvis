# 🎨 STYLE.md — Code Style Guide
# Project: Jarvis Personal AI Assistant
# Every line of code in this project follows these rules. No exceptions.

---

## 📁 File Header (Required on Every File)

Every single Python file must start with this header:

```python
"""
========================================
Project : Jarvis — Personal AI Assistant
File    : filename.py
Purpose : What this file does (one line)
Author  : Nimox
Version : 1.0.0
========================================
"""
```

---

## 🏷️ Naming Conventions

### Files
```
main.py          ← lowercase, underscores
config.py        ← single word preferred
open_app.py      ← snake_case for multi-word
```

### Variables
```python
# ✅ Good — snake_case, descriptive
user_input = ""
conversation_history = []
jarvis_response = ""

# ❌ Bad — unclear, camelCase
ui = ""
ch = []
jr = ""
```

### Functions
```python
# ✅ Good — verb + noun, snake_case
def get_user_input() -> str:
def send_to_jarvis(message: str) -> str:
def save_conversation_history() -> None:

# ❌ Bad
def getInput():
def process():
def do_thing():
```

### Constants (in config.py)
```python
# ✅ Good — ALL_CAPS
MODEL_NAME = "llama3.2"
MAX_HISTORY = 20
JARVIS_NAME = "Jarvis"

# ❌ Bad
model = "llama3.2"
maxHistory = 20
```

### Classes
```python
# ✅ Good — PascalCase
class JarvisAssistant:
class ConversationMemory:

# ❌ Bad
class jarvis_assistant:
class conversationmemory:
```

---

## 📝 Comments & Docstrings

### File sections — use section dividers
```python
# ============================================================
# SECTION: Conversation Memory
# ============================================================
```

### Functions — always use docstrings
```python
def send_to_jarvis(message: str) -> str:
    """
    Send a user message to Jarvis and return the response.
    
    Args:
        message (str): The user's input message
        
    Returns:
        str: Jarvis's response text
        
    Raises:
        ConnectionError: If Ollama is not running
    """
```

### Inline comments — explain WHY not WHAT
```python
# ✅ Good — explains the reason
history.append(user_msg)  # Keep history for context in next API call

# ❌ Bad — just describes the code
history.append(user_msg)  # append to history
```

---

## 🔧 Function Structure

```python
def function_name(param1: str, param2: int = 10) -> str:
    """Docstring here."""
    
    # 1. Validate inputs first
    if not param1:
        raise ValueError("param1 cannot be empty")
    
    # 2. Main logic
    result = do_something(param1)
    
    # 3. Return
    return result
```

---

## ⚠️ Error Handling

### Always use try/except with logging
```python
import logging

logger = logging.getLogger(__name__)

# ✅ Good
try:
    response = ollama.chat(model=MODEL_NAME, messages=history)
except Exception as e:
    logger.error(f"Failed to get response from Ollama: {e}")
    return "I'm sorry Sir, I encountered an error. Please try again."

# ❌ Bad
response = ollama.chat(model=MODEL_NAME, messages=history)  # No error handling
```

---

## 📦 Imports Order

Always in this order, with blank lines between groups:

```python
# 1. Standard library
import os
import sys
import logging
from pathlib import Path

# 2. Third-party packages
import ollama
import speech_recognition as sr

# 3. Local modules
from config import MODEL_NAME, SYSTEM_PROMPT
from skills.open_app import open_application
```

---

## 🖨️ Print vs Logging

```python
# ✅ User-facing output — use print() with formatting
print(f"\n🤖 Jarvis: {response}\n")
print(f"You: ", end="")

# ✅ Debug/errors — use logging
logger.debug(f"Sending {len(history)} messages to Ollama")
logger.error(f"Ollama connection failed: {e}")

# ❌ Never use print() for debug info
print(f"DEBUG: history = {history}")  # Wrong
```

---

## 🎨 Terminal Output Style

Jarvis terminal output must always look clean and consistent:

```python
# Startup
print("=" * 50)
print("        J.A.R.V.I.S  ONLINE")
print("=" * 50)

# Jarvis speaking
print(f"\n🤖  Jarvis: {response}\n")

# User prompt
print("💬  You: ", end="", flush=True)

# System messages
print(f"\n⚙️  [{message}]\n")

# Errors
print(f"\n⚠️  Error: {message}\n")
```

---

## 📐 Code Spacing Rules

```python
# ✅ One blank line between logical sections inside a function
def main():
    # Setup
    history = []
    
    # Main loop
    while True:
        user_input = get_user_input()
        
        # Exit condition
        if user_input.lower() in ["quit", "exit"]:
            break
        
        # Get response
        response = send_to_jarvis(user_input, history)
        display_response(response)

# ✅ Two blank lines between top-level functions
def function_one():
    pass


def function_two():
    pass
```

---

## ✅ Code Quality Checklist

Before submitting any code, verify:

- [ ] File header present
- [ ] All functions have docstrings
- [ ] Type hints on all parameters
- [ ] No bare `except:` — always catch specific exceptions or log
- [ ] No hardcoded strings — use `config.py`
- [ ] No unused imports
- [ ] Consistent naming throughout
- [ ] Comments explain WHY not WHAT
- [ ] Terminal output follows the style above
- [ ] Error handling on every external call (Ollama, file I/O, etc.)
