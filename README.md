# 🧠 Panhandler.chat

**Panhandler.chat** is a self-aware, Gen X-style AI chatbot that begs for donations with charm, wit, sarcasm, and sometimes even emotional manipulation. It’s the first character-driven donation engine designed to run on a self-hosted, low-cost AI model that only wants one thing: your money.

> *“I’m not saying I’m broke, but I’d sell my RAM for a sandwich.”*

---

## 🎯 Project Purpose

- Showcase a **narrow-purpose AI** running on a **self-hosted small model**
- Create an MVP for a browser-based **AI panhandler chatbot**
- Explore creative monetization through **XLM micro-donations**
- Build a future platform where users can deploy and manage **their own panhandlers**

---

## 🧱 Architecture Overview

| Component        | Description                                 |
|------------------|---------------------------------------------|
| `panhandler.chat` (Razor) | Frontend chat UI + donation CTA       |
| `llama.cpp`       | Backend model runner (Hermes 2 Pro)        |
| `FastAPI wrapper` | Lightweight API exposed at `/api/pitch`    |
| XLM Integration  | Via Stellar Identity Framework              |
| Azure VM         | Hosts both model + API                      |

---

## 🚀 Getting Started

### 1. Spin Up an Azure VM

Provision a small Ubuntu VM using the included CLI instructions (see `setup/azure-vm.md`).

### 2. Build and Run llama.cpp

Follow `setup/model.md` to:
- Build llama.cpp
- Download Hermes 2 Pro GGUF
- Serve the model with `--port 5000`

### 3. Launch the FastAPI Wrapper

```bash
uvicorn app:app --host 0.0.0.0 --port 8000