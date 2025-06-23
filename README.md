# Discord + Local LLM Bot (MSTY) – Simple Setup Guide (NVIDIA + Intel Only, AMD users can get fucked)

This guide explains how to run a **fully local AI chatbot** inside your Discord server using **MSTY** and a small amount of scripting. No subscriptions, just your own machine.

The bot runs from Windows using a batch file and `bot.py`, which you'll download and configure yourself.

---

## 1. Create a Discord Bot

1. Go to [https://discord.com/developers/applications](https://discord.com/developers/applications)
2. Click "New Application" → name your bot (e.g. "Arielle" or anything)
3. In the sidebar, go to "Bot" → click "Add Bot"
4. Under "Privileged Gateway Intents":

   * Enable **Message Content Intent**
5. Copy your **Bot Token** and **save it securely**
6. In the sidebar, go to "OAuth2" → "URL Generator":

   * Scopes: `bot`
   * Bot Permissions: `Send Messages`, `Read Message History`
   * Copy the generated URL and open it in your browser
   * Add the bot to your server

---

## 2. Install MSTY and Your Model

1. Download MSTY from:
   [https://msty.app](https://msty.app/) (Windows version)

2. Launch MSTY and go through first-time setup

3. In MSTY, open the **Model Downloader** (sidebar)

   * Choose a model that fits your system (e.g. `llama3.2:1b`, `Mistral-Instruct`, etc.)
   * I strongly recommend Llama-3.2-3B-Instruct-abliterated
   * For most people with 16–64GB RAM: use **Q4\_K\_M** quantized models
   * Let MSTY download and install the model

4. Once installed, go to **Settings → Local AI**

   * Make sure your model is selected
   * Set context size (e.g. 8192), batch size (16), and threads (20 or more if you have a multi-core CPU)
   * Make sure **Service Endpoint** is: `http://localhost:5000/v1/chat/completions`
   * Enable local access if not already on

---

## 3. Customize the Files

You should now have:

* `bot.py`
* `start_bot_and_msty.bat`

Customize these:

### In `bot.py`:

* Replace the placeholder `DISCORD_TOKEN` value with your actual bot token

* Set your model name (must match what MSTY shows, e.g. `"llama3.2:1b"`)

* Customize the `PERSONALITY` variable to define how your bot behaves.

* You can adjust history size (`MAX_HISTORY_MESSAGES = 100`) if needed

### In `start_bot_and_msty.bat`:

* Set correct paths for:

  * MSTY executable
  * Python executable
  * Location of `bot.py`
* Match the `MODEL_NAME` to what you're using (e.g. `llama3.2:1b`)
* You can adjust warm-up message or personality prompt as needed

---

## 4. Start the Bot

1. Double-click `start_bot_and_msty.bat`

2. It will:

   * Start MSTY minimized
   * Wait until MSTY is ready
   * Warm up the model
   * Launch the Discord bot

3. In your Discord server, mention the bot:

   * `@YourBotName hello`
   * It should respond with your custom personality and remember your past messages

---

## Optional

* **Persistent memory**: By default, the bot saves user conversations to disk in a `history/` folder. To clear a user's memory, delete their `.json` file from that folder.
* **Model switching**: Just change the `MODEL_NAME` in both files and update the model in MSTY.
* **GPU offload**: In MSTY's Local AI settings, you can offload a few layers to GPU if you have one (optional; weak GPUs with 4GB or less of VRAM (for example, 1050 Ti, GTX 1650 (all variants), Quadro P1000, NVIDIA T400, NVIDIA T600) should use 0–4 layers).
* **Auto start**: You can add a shortcut to `start_bot_and_msty.bat` to Windows startup folder.

---

That’s it — no money, no BS, full control, using only Discord and your PC.

Enjoy your fully local chatbot.

##TODO:
* Bundle python and configure one time batch file

**DISCLAIMER**

This project is provided **as-is** for **educational and non-commercial use only**. By using, modifying, or redistributing the contents of this repository, you agree to the following:

* The author of this project **assumes no responsibility** for how this software is used.
* You are **solely responsible** for complying with all applicable laws and regulations in your jurisdiction.
* This software must **not** be used for illegal activity, harassment, surveillance, misinformation, or any malicious purpose.
* The author is **not liable** for any damages, losses, or consequences arising from the use or misuse of this project.
* By using this project, you agree that any **misuse or abuse** of its capabilities is **not the responsibility** of the author.

This tool is intended strictly for **personal, local experimentation** and should not be used in any system where safety, legal compliance, or ethical considerations are critical.
