# DiscordChatbotsForDummies

**A zero‑configuration installer for connecting your local MSTY LLM to a Discord bot** — no Docker, no servers, no fluff. Just follow these steps and you're ready to chat with your custom AI assistant.

## What It Does

This project wraps everything into one simple installer that:

* Sets up your Discord bot with MSTY (Meta LLaMA 3.2) locally
* Takes care of Python installs, path configuration, and file generation
* Creates startup scripts ready to run and keep your bot online

## Why It Exists

Because getting AI in Discord shouldn’t require DevOps skills. With **DiscordChatbotsForDummies**, anyone can launch a local‑hosted, fully functional AI bot in minutes — no cloud, no fees, no fuss.

## Quick Start

1. **Create a Discord bot account** on the Developer Portal.
2. **Install Python 3.10+**, making sure to add it to your PATH.
3. **Download and install MSTY** with the default Meta LLaMA 3.2 model.
4. **Run the installer** — just follow the prompts (token, paths, preferences).
5. Launch your bot using the generated `start_bot_and_msty.bat`.

**Optional**: Add a shortcut to the `start_bot_and_msty.bat` file into your Windows Startup folder so your bot runs automatically when you log in.

---

## Features

* 💡 Smart installer prompts for Discord token, MSTY path, LLM name, port, memory settings, personality, and more.
* 🔒 Built‑in validation ensures correct token length and Python version.
* 🧠 Automatically assembles `bot.py`, `start_bot_and_msty.bat`, and `requirements.txt` based on your inputs.
* 🧾 Saves settings in `bot_config.json` for easy reuse or sharing.
* 💾 Supports per‑user and per‑channel long‑term chat memory.
* 🕰 Adds time stamps and UTC offset to every prompt.
* 🙅 Enforces personality rules, prevents self‑narration, and manages LLM denial.
* 🚫 AMD exclusion notice (“Intel + NVIDIA only”) for clarity and help‑desk jokes.

---

**DiscordChatbotsForDummies**: finally, an AI‑in‑Discord installer you don’t have to be a coder to use.

## DOWNLOAD

https://github.com/ZoeyKL/DiscordChatbotsForDummies/releases/tag/DiscordChatbotForDummies1.2FINAL
