# Jarvis Terminal Chat Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Add a one-file terminal chat loop for the local Jarvis assistant.

**Architecture:** `jarvis\main.py` will keep a system message and all same-session user/assistant turns in a list passed to `ollama.chat`. It will print the project-defined time-of-day welcome, then read and respond to terminal input until `quit` or `exit`.

**Tech Stack:** Python 3.13, standard library, `ollama` Python package.

**Spec:** `project.md` and the conversation-approved design for this request.

## Global Constraints

- Use Python 3.13.3 and Ollama 0.40.16, per `project.md`.
- The AI model is `llama3.2`.
- Use only the Ollama Python package for AI calls; no cloud AI APIs or other AI libraries.
- Always include the Jarvis system prompt in every Ollama call.
- Keep code clean and commented; add no unrequested features.
- Deliver only `jarvis\main.py` as runtime code.

## Review Focus

- Exit commands should be case-insensitive and recognized after trimming whitespace; verify `quit`, `exit`, and padded uppercase input.
- Blank input should not be sent to the model; verify it simply prompts again.
- Prior turns must reach the next model call; verify the second call includes the first user and assistant messages.
- Ollama failures should remain visible rather than producing a fabricated reply; verify the exception is not swallowed.
- End-of-input should terminate cleanly; verify EOF does not produce an infinite loop.

---

### Task 1: Create Jarvis terminal chat

**Files:**
- Create: `jarvis\main.py`
- Test: temporary in-memory test harness; do not add a test file

**Interfaces:**
- Consumes: `ollama.chat(model="llama3.2", messages=messages)`
- Produces: executable `main.py` terminal loop

- [ ] **Step 1: Exercise the required loop behaviors with a temporary failing test harness**

  Assert that `quit` and `exit` stop the loop, normal input calls `ollama.chat`, the next call contains earlier user and assistant messages, and the system message is present. Also check blank input, Ollama exceptions, and EOF behavior.

- [ ] **Step 2: Run the harness and verify it fails because `jarvis\main.py` does not yet exist**

- [ ] **Step 3: Implement `jarvis\main.py`**

  Use the documented system prompt verbatim; include a small standard-library helper to select the welcome greeting by local time. Normalize terminal input for blank and exit handling. Append each user message and the returned assistant content to the same `messages` list, and print the model response.

- [ ] **Step 4: Run the harness and Python syntax validation**

  Expected: all behavioral assertions pass and `python -m py_compile jarvis\main.py` succeeds.
