# ⚡ Interview Quick Answer Assistant (QAA)


# https://ai-qaa-hybrid.github.io/frontend

> **The Privacy-First, Hybrid Knowledge Engine for Live Technical Interviews & Rapid Engineering Recall.**

QAA is a stealth, low-latency interview companion engineered for high-stakes technical interviews, live coding sessions, and rapid architectural revision. Built around a **single-hotkey contract workflow**, it bridges local instant search with multi-LLM streaming fallbacks to deliver precise, structured answers in milliseconds.

---

## 🎯 Why QAA? (The Core Problem)

In live technical interviews or fast-paced technical assessments:
1. **Typing or Searching in Real-Time is Fatal:** Clicking through menus, switching tabs, or typing lengthy prompts into standard AI interfaces wastes crucial seconds and distracts your focus.
2. **Context Switching Kills Flow:** Long-winded, chatty AI responses require too much time to scan while actively talking to an interviewer.
3. **Data Privacy & API Leak Risks:** Developers often hesitate to paste custom interview notes, proprietary system designs, or personal resume details into third-party cloud tools.

### 💡 The Solution

QAA converts **single-letter hotkeys** into strict, format-enforced **Answer Contracts**. With a single keypress, your voice or typed query instantly routes through a **local sub-10ms search engine**, falling back seamlessly to top-tier LLM streaming models only when local knowledge misses.

---

## 🚀 Key Features & Highlights

### 1. ⚡ Hybrid Search & Smart Multi-LLM Routing
- **Sub-10ms Local-First Search:** Searches through bundled and custom JSON knowledge bases instantly using fuzzy matching and conversational filler stripping.
- **Multi-LLM Provider Support:** Seamlessly connect and toggle between leading LLM providers (**Google Gemini, Groq, OpenAI**) using your own API keys.
- **Streaming LLM Fallback:** If local search yields a miss, the system automatically falls back to your configured LLM while strictly maintaining the hotkey's format contract.

### 2. 🎯 Binding Hotkey Answer Contracts
| Hotkey | Answer Contract | Output Guarantee |
| :---: | :--- | :--- |
| **`D`** | **Definition** | 1 concise definition sentence + 2–4 clean bullet points. Zero fluff. |
| **`C`** | **Code Example** | 1 production-ready code snippet + concise explanation. |
| **`I`** | **Comparison** | Feature matrix markdown table + 1-sentence bottom-line takeaway. |
| **`E`** | **Practical Example** | Real-world scenario breakdown (**Problem $\rightarrow$ Solution $\rightarrow$ Impact**). |
| **`Q`** | **Verbal Answer** | First-person, highly speakable response (40–70 words, natural interview cadence). |
| **`K`** | **Key Points** | 3–5 high-yield revision bullet points for rapid scanning. |

### 3. 🌐 Native Bilingual & Devanagari Support
- **Full Hindi & English Voice Recognition:** Toggle voice input seamlessly between `en-US`, `en-IN`, and `hi-IN`.
- **Conversational Filler Stripping:** Automatically strips spoken fillers (*"क्या है"*, *"किसे कहते हैं"*, *"what is"*, *"can you explain"*) before performing search queries.
- **Typography Engine:** Integrated `Noto Sans Devanagari` font rendering prevents matra and ligature clipping.

### 4. 🔒 Zero-Downtime Privacy & WebCam Stealth
- **100% Client-Side Architecture:** Zero server-side data logging or telemetry tracking.
- **Local Key Isolation:** API keys and local knowledge base overrides are stored exclusively in browser `localStorage`.
- **Stealth Visual Theme (`#0b0f19`):** High-contrast, anti-glare dark palette designed to eliminate monitor glare reflected on webcams during video calls.

---

## 🔮 Roadmap & Upcoming Features (Work in Progress)

We are actively expanding QAA from a local assistant into a personalized, syncable technical knowledge platform:

* 🔐 **Secure User Authentication (In Progress):** Multi-device synchronization and secure user profiles via auth integration.
* 🧠 **Personalized Knowledge Hub:** Ability to import personal resumes, system design notes, and custom project summaries into your personal vault.
* 🛡 **Role-Based Feature Toggles:** Public demo instances currently operate in **Guest Mode** (with specific custom override features disabled to ensure data security and platform stability).
* ⚡ **Context-Aware Retrieval:** Semantic retrieval over user-uploaded documents with strict local privacy boundaries.

---

## ⌨️ Control & Navigation Cheatsheet

| Shortcut | Action |
| :--- | :--- |
| **`D`, `C`, `I`, `E`, `Q`, `K`** | Trigger hotkey contract & start instant voice listening |
| **`Escape`** | Cancel speech listening / Clear active query / Close modals |
| **`/`** | Focus manual search bar (typing fallback) |
| **`Y`** | Copy current markdown answer to clipboard |
| **`S`** | Toggle Settings & Knowledge Manager |
| **`?`** | Open Shortcuts Cheatsheet |
| **`Enter`** | Submit typed search query |

---

## 🏗️️ Architecture Overview

```text
src/
├── core/                   # Pure Domain Logic (Zero Framework / DOM Dependencies)
│   ├── search/             # Normalizer, Levenshtein, Sub-10ms Local Search Engine
│   ├── speech/             # Web Speech API Adapter with Silence Guards
│   ├── llm/                # Multi-Provider Direct-Fetch SSE Streaming Client
│   └── storage/            # Local Knowledge Store & Config Management
├── data/                   # Bundled Initial Knowledge Base (JSON)
└── ui/                     # Presentation Layer (React 19 + Tailwind 4)

---

## 🤝 Open Source & Licensing

Designed with ❤️ for developers, software engineers, and technical interview candidates.
