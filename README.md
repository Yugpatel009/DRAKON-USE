# DRAKON AI - Official User Manual

Welcome to **DRAKON AI**, your intelligent, privacy-first coding assistant! DRAKON combines the power of cloud-based AI (Groq) with completely offline, local execution using Ollama.

This manual will guide you step-by-step on how to download, set up, and use the DRAKON standalone Windows executable (`.exe`), including installing the necessary engine and setting up the local AI models.

---

## Table of Contents
1. [Prerequisites](#1-prerequisites)
2. [Step 1: Download & Run the DRAKON `.exe`](#2-step-1-download--run-the-drakon-exe)
3. [Step 2: Install the Ollama Engine](#3-step-2-install-the-ollama-engine)
4. [Step 3: Download & Set Up the Local AI Model](#4-step-3-download--set-up-the-local-ai-model)
5. [Using DRAKON AI (Cloud vs Local)](#5-using-drakon-ai-cloud-vs-local)
6. [Troubleshooting & FAQs](#6-troubleshooting--faqs)

---

## 1. Prerequisites
- **Operating System:** Windows 10 or Windows 11
- **Hardware:** A modern CPU is required. For the best local model experience, a dedicated GPU (NVIDIA with CUDA support) is highly recommended.
- **Storage:** At least 8-10 GB of free space. The app itself is small, but local AI models (like *Hushiyar-Alpha*) require several gigabytes.
- **Internet:** Required initially to download the application and the models. After setup, the local models can be completely used **offline**.

---

## 2. Step 1: Download & Run the DRAKON `.exe`

DRAKON is built as a portable Windows executable for maximum performance and deep OS integration.

1. **Download the App:** Navigate to the DRAKON download page in your browser or receive the `.exe` file distributed by the creator.
2. **Where to Place It:** Move the `DRAKON.exe` to a dedicated folder, for example: `C:\Program Files\Drakon\` or simply run it from your `Desktop`.
3. **Run the App:** Double-click `DRAKON.exe` to launch the application. 
   *(Note: If Windows SmartScreen displays a "Windows protected your PC" warning, click **More info** and then click **Run anyway**, as this is a new piece of software.)*

---

## 3. Step 2: Install the Ollama Engine

While the DRAKON app handles the user interface and cloud requests, it requires **Ollama** running in the background to serve the local AI models directly on your hardware.

1. **Download Ollama:** Head to the official website: [https://ollama.com/download](https://ollama.com/download)
2. Select **Windows** and download the installer (`OllamaSetup.exe`).
3. **Install:** Run `OllamaSetup.exe` and follow the standard installation prompts.
4. **Verify it's running:** Look at your Windows System Tray (bottom right corner of your screen, near the clock). You should see the cute little llama icon. This means the Ollama engine is active.

---

## 4. Step 3: Download & Set Up the Local AI Model

DRAKON supports many open-source models (Mistral, Llama 3, Gemma), but it is heavily optimized for a custom reasoning model called **Hushiyar-Alpha**. 

Here is how to download and set it up:

1. Open your **Command Prompt** (Press `Win + R`, type `cmd`, and hit Enter) or **PowerShell**.
2. **Download the model** by copying and pasting the following command:
   ```bash
   ollama pull aryanvala/hushiyar-alpha
   ```
   *Wait for the download to finish. Depending on your internet speed, this might take a few minutes as the model is several gigabytes in size.*

3. **Verify the installation** by running:
   ```bash
   ollama run aryanvala/hushiyar-alpha
   ```
   You can send a quick message in the terminal just to see if it responds. Once it does, type `/bye` to exit. The model is now permanently saved on your PC!

---

## 5. Using DRAKON AI (Cloud vs Local)

Launch `DRAKON.exe` and you'll be greeted by the chat interface. At the bottom right, you'll see a **Model Selection Menu** (click the robot icon).

### Zenith (Cloud Model)
- **What is it:** Powered by Groq LPU™ and Llama 3.3.
- **Speed:** Blazing fast (< 300ms latency).
- **Use Case:** Best for heavy coding tasks, intense logic, and when you have a stable internet connection.

### Hushiyar-Alpha (Local Model)
- **What is it:** The model you just downloaded locally.
- **Speed:** Depends on your PC's hardware (GPU/RAM).
- **Use Case:** 100% Data Privacy. Works completely offline. Best for working on proprietary codebases or when you lack an internet connection.

### Features Available to You:
- **Code Generation:** Just ask DRAKON to write a script or function in natural language.
- **Smart Debugging:** Paste an error log, and DRAKON will explain what failed.
- **File Uploads:** Use the `+` button next to the chat bar to attach code files, PDFs, or Image assets. Note: The cloud model has built-in vision integration.
- **Deep Think Mode / Image Generation:** Click the `+` options menu to switch modes depending on your creative needs.

---

## 6. Troubleshooting & FAQs

**Q: DRAKON says "Ollama Not Running" in the model selector.**
A: Make sure the Ollama app is open. Search for "Ollama" in your Windows Start Menu and click it. Ensure the llama icon is in your system tray.

**Q: The local model is replying very slowly.**
A: Local LLMs are hardware intensive. If you do not have a dedicated GPU, Ollama will fall back to using your RAM/CPU, which is significantly slower. Be sure to close memory-heavy apps to speed it up.

**Q: How do I update my local model?**
A: Open your terminal and simply run `ollama pull aryanvala/hushiyar-alpha` again. It will automatically download the newer layers and replace the old ones.

**Q: Are my files safe?**
A: When you use the local `Hushiyar-Alpha` model, your prompts, code files, and documents never leave your computer. They are processed entirely locally. If you use the `Zenith` cloud model, they are sent securely to the API for rapid processing.
