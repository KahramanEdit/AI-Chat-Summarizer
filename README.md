<div align="center">

# 🎮 AI-Chat-Summarizer

**One-Click AI Conversation Extractor & Technical Handoff Summarizer (Manifest V3)**

[![Manifest](https://img.shields.io/badge/Manifest-V3-2563eb?style=for-the-badge&logo=googlechrome&logoColor=white)](https://developer.chrome.com/docs/extensions/mv3/)
[![Platforms](https://img.shields.io/badge/AI-DeepSeek%20%7C%20Gemini%20%7C%20Claude%20%7C%20Copilot%20%7C%20ChatGPT-4f46e5?style=for-the-badge)](#supported-platforms)
[![Engine](https://img.shields.io/badge/Engine-Gemini%202.5%20Flash%20%2F%20Local-10b981?style=for-the-badge)](#dual-mode-architecture)
[![Author](https://img.shields.io/badge/Author-Clenix%20%2F%20Kahraman-111827?style=for-the-badge)](https://github.com/KahramanEdit)

</div>

---

## 📌 Overview

**AI-Chat-Summarizer** is a lightweight, privacy-focused Chromium extension (Chrome, Edge, Brave, Kiwi/Mises) designed to solve context-window and message-limit lockouts across AI platforms. With a single click, it scrapes the active chat tab—preserving code blocks while stripping UI noise—and copies a structured handoff summary directly to your clipboard so you can seamlessly resume work in another AI session.

---

## ✨ Key Features

* **⚡ One-Click Extract & Auto-Copy:** Parses the active tab and immediately copies the formatted output to your clipboard.
* **🌐 Multi-Platform & Shadow DOM Support:** Dedicated parsers for **DeepSeek**, **Google Gemini**, **Claude**, **Microsoft Copilot** (including Shadow DOM components), and **ChatGPT**, plus a universal fallback for Grok, Perplexity, and Qwen.
* **💻 Code Block Preservation:** Converts `<pre><code>` blocks into clean Markdown fenced code blocks with language tags intact.
* **🔄 Dual-Mode Engine:**
  * **Zero-Config Local Handoff Mode:** Works immediately without an API key by packaging the cleaned transcript with a structured continuation prompt.
  * **AI Compression Mode (Optional):** Uses a free **Google AI Studio (`gemini-2.5-flash`)** API key to condense long conversations into a concise technical handoff summary.
* **🛡️ Automatic Fallback Protection:** If the API quota is exceeded or a network error occurs, the extension automatically falls back to copying the full cleaned handoff transcript.
* **💾 Export Options:** Includes one-click re-copy and `.txt` file download buttons.

---

## 📂 Project Structure

```text
AI-Chat-Summarizer/
├── manifest.json   # Manifest V3 config & permissions
├── content.js      # Deep Shadow DOM chat parser
├── popup.html      # Dark-mode extension popup UI
└── popup.js        # Clipboard, export & Gemini API logic
```

---

## 🚀 Installation

1. Clone or download this repository to your computer:
   ```bash
   git clone [https://github.com/KahramanEdit/AI-Chat-Summarizer.git](https://github.com/KahramanEdit/AI-Chat-Summarizer.git)
   ```
2. Open your Chromium browser and navigate to:
   ```text
   chrome://extensions
   ```
   *(For Microsoft Edge, open `edge://extensions`)*
3. Enable **Developer mode** in the top-right corner.
4. Click **Load unpacked** and select the `AI-Chat-Summarizer` folder.
5. Pin **AI Sohbet Özetleyici** to your browser toolbar.

---

## ⚙️ Usage & Optional API Setup

1. Open any active AI chat tab (DeepSeek, Gemini, Claude, Copilot, or ChatGPT).
2. Click the extension icon and press **⚡ Özetle ve Panoya Kopyala**.
3. Paste (`Ctrl + V`) the copied handoff note into any new AI chat window.

### Enabling AI Compression Mode (Optional)
* Expand **⚙️ Yapay Zeka Özet Motoru** at the bottom of the popup.
* Paste a free API key from [Google AI Studio](https://aistudio.google.com/apikey) and click **Anahtarı Kaydet**.
* Your key is stored locally via `chrome.storage.local` and is never sent anywhere except Google's official Generative Language API.

---

## ⚠️ Disclaimer & No Liability

* **Use at your own risk.**
* **Developer accepts NO responsibility for bricked devices**, browser instability, API quota usage, or unintended exposure of sensitive conversation data when sharing transcripts with third-party AI providers.
* This project is an independent utility and is not affiliated with OpenAI, Google, Anthropic, DeepSeek, or Microsoft.
* **Author:** Clenix / Kahraman (`KahramanEdit`)
