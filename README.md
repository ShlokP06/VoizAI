# VoizAI · Next-Generation Voice Intelligence Platform

<p align="center">
  <img src="Frontend/assets/logo.png" alt="VoizAI Logo" width="200"/>
</p>

<p align="center">
  <strong>Seamless voice-driven interaction · Real-time intelligence · Modular architecture</strong>
</p>

---
[License: Apache 2.0](LICENSE)

## ✨ Overview

**VoizAI** is an advanced **voice-first AI assistant platform** engineered for real-time interaction, natural conversation, and dynamic task execution.  
It combines **speech recognition**, **intent classification**, and a **tool-driven agent framework** to create a system that feels both **intuitive** and **powerful** — whether controlling your environment, automating workflows, or answering complex questions.

Built with a modular design, VoizAI serves as both a **reference implementation of a modern AI voice agent** and a **foundation for extensible, production-grade deployments**.

---

## 🌐 Key Capabilities

- 🎙 **Conversational Voice Interface** — Hands-free, natural, and responsive.  
- 🧠 **Intent Recognition & Orchestration** — Classifies queries and dispatches to the right module or tool.  
- 🛠 **Dynamic Tool Integration** — Plug in custom tools for system control, app launching, or external APIs.  
- 🔎 **Knowledge & Web Access** — Fetches answers and contextual information on demand.  
- ⚡ **Real-Time Processing** — Optimized backend for low-latency interactions.  
- 🖥 **Cross-Platform Ready** — Web-based frontend with modular backend design.  
- 🔒 **Secure & Configurable** — API keys, credentials, and runtime settings are environment-driven.  

---

## 🏗 Architecture
```bash
                ┌────────────┐
 🎤 Speech ───▶ │ Frontend UI │ ───▶ WebSocket/REST
                └──────┬─────┘
                       │
                ┌──────▼─────┐
                │   Backend  │
                │   (src/)   │
                ├────────────┤
                │ Speech I/O │
                │ Intent Clf │
                │ Agent Core │
                └──────┬─────┘
                       │
                ┌──────▼─────┐
                │ Agent Tools│
                │  (plugins) │
                └────────────┘
```
- **Frontend** — Captures speech, provides interactive UI.  
- **Backend Core** — Manages recognition, intent classification, orchestration.  
- **Agent Tools** — Modular plug-ins that implement system control, app launching, web search, etc.  

---

## 📂 Repository Layout
```bash
VoizAI/
├── Frontend/ # Web UI layer (voice capture, interface)
├── src/ # Core backend (speech, intent, orchestration)
│ ├── main.py # Entry point
│ ├── speech.py # Speech recognition & synthesis
│ ├── intent_classifier.py
│ └── ...
├── agent_tools/ # Tool modules (system control, web, apps)
├── requirements.txt
└── README.md
```
---

## ⚙️ Installation & Setup

### Prerequisites
- **Python 3.9+**
- **HTML, CSS, JavScript for Frontend**  
- **API keys** for speech / LLM providers (e.g. OpenAI, Whisper, etc.)  

### Quickstart

```bash
# Clone repository
git clone https://github.com/ShlokP06/VoizAI.git
cd VoizAI

# Create virtual environment
python3 -m venv venv
source venv/bin/activate   # macOS/Linux
venv\Scripts\activate      # Windows

# Install dependencies
pip install -r requirements.txt
```

## Configure Environment
In the .env file present in the /src folder, add all the required API keys:
```bash
SPOTIFY_CLIENT_ID= "YOUR_CLIENT_ID"
SPOTIFY_CLIENT_SECRET= "YOUR_CLIENT_SECRET"
YOUTUBE_API_KEY="YOUR_API_KEY"
GROQ_API_KEY = "YOUR_API_KEY"
CLAUDE_API_KEY = "YOUR_API_KEY"
ANTHROPIC_API_KEY = "YOUR_API_KEY"
HF_TOKEN = "YOUR_HF_KEY"
```

## Launch Backend
```bash
python src/main.py
```

## Launch Frontend
```bash
cd Frontend
python -m http.server 8080
```

## Usage
Once running, VoizAI supports commands such as:
- **Open Youtube** -> Launches YouTube in browser
- **Turn up the brightness** -> Performs system control to change display brightness.
- **Who is the CEO of Tesla** -> Web search + Answer Synthesis
Every request flows through:
1. **Speech Recognition** using Speech-to-Text (STT) Engine
2. **Intent Classifier**, parses the inputted command and helps in selection of the appropriate tool to be used.
3. **Agent execution** - the selected tool is used to perform the required procedure, and the generated response is passed through a Text-to-Speech(TTS) Engine to generate audio responses.




