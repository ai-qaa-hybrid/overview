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
- **Multi-LLM Provider Support:** Connect **Google Gemini, Groq, OpenAI, or OpenRouter** with your own API key. A custom base URL is also supported. The model is used only when the topic is not already in the local set.
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

### 3. 🌐 Recognition Language, Subjects, and Theme
- **One recognition language for every question.** The default is `en-IN`. You can switch to `en-US` or `en-UK` (`en-GB` in the browser).
- **Subjects come from the knowledge files.** A file such as `javascript` or `react` becomes a subject, and the Questions page groups each category by subject.
- **Light and dark themes.** The header button names the theme it will turn on: **Light** switches to the light theme, **Dark** switches to the dark theme. In Settings, the highlighted choice is the theme that is on now.
- **Conversational filler stripping:** Spoken prefixes such as “what is” and “difference between” are removed before search.
- **Typography:** `Noto Sans Devanagari` is loaded so Indic text does not clip.

### 4. 🔒 Browser-Only Notes and a Locked Export
- **100% client-side.** There is no application server and no telemetry.
- **Add, Edit, and Import stay in this browser.** They are saved in `localStorage` and do not rewrite the bundled JSON files. Another visitor does not see your changes.
- **Reset Knowledge to Defaults** deletes that browser copy and shows the original bundled topics again.
- **Export stays disabled** so the original knowledge cannot be downloaded as a file.
- **API keys** stay in this browser and are sent only to the provider you select.
- **Live app:** [https://ai-qaa-hybrid.github.io/frontend/](https://ai-qaa-hybrid.github.io/frontend/)

---

## 🔮 Roadmap & Upcoming Features (Work in Progress)

We are actively expanding QAA from a local assistant into a personalized, syncable technical knowledge platform:

* 🔐 **Sign-in:** Not built yet. Personal topics already stay in the browser. Accounts would later sync that library across machines.
* 🧠 **Token budgets:** A future server-side proxy would hold provider keys and cap usage per person. Today there is no shared token wallet. A local hit uses zero model tokens. A miss with a key streams one answer, capped at 500 tokens by default, and aborts after 8 seconds.
* ⚡ **Code splitting:** The syntax highlighter is still in the main bundle. Loading it only for code answers is open work.

---

## ⌨️ Control & Navigation Cheatsheet

| Shortcut | Action |
| :--- | :--- |
| **`S`** | Turn voice on or off |
| **`D`, `C`, `I`, `E`, `Q`, `K`** | While voice is on, hold the key and speak. You can let go while you talk |
| **`Escape`** | Turn voice off, clear the screen, and close Settings |
| **`/`** | Focus the search field |
| **`Enter`** | Submit the typed topic for the selected category |
| **`Y`** | Copy the current answer |
| **Settings** | Opened from the Settings button, not a hotkey |

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
