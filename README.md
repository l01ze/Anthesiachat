# 🏛️ Athena · Multi‑Agent AI Studio

A browser‑based, fully client-side multi-agent studio designed to orchestrate, customize, and deploy multiple AI agents simultaneously (powered by Groq’s Llama 3.3‑70B). Athena features persistent conversations, intelligent delegation, automatic memory extraction, full message history editing, and collapsible reasoning blocks.

> 🌿 **Separate Branch Available:** **Dolphin Uncensored (v2.0)** – A standalone single-agent chat leveraging the distributed AI Horde network to run unrestricted open-source models completely registration-free.

---

## ⚠️ Important Configuration Note
All historical releases contain a placeholder/revoked API key. To run the application, open the file and replace `"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"` with your personal Groq key. You can get one for free at **[console.groq.com](https://console.groq.com)**.

---

## 📸 Interface Preview

<img width="1919" height="998" alt="Athena Multi-Agent UI Overview" src="https://github.com/user-attachments/assets/88b2c32a-ca25-497f-b550-d57a2ff13258" />

---

## 📅 Version History Matrix

| Version | Improvements | Advantages | Disadvantages |
| :--- | :--- | :--- | :--- |
| **1.0** | Initial multi‑agent system with basic delegation (`[DELEGATE]`), retrieval (`[RETRIEVE]`), `<thinking>` tags, sidebar navigation, and `localStorage` persistence. | Fully functional offline foundation; cross-agent collaboration; code block copy triggers. | No history editing; lacks 3‑dot chat menus; code truncation bugs during delegation blocks. |
| **1.1** | Collapsible delegation interfaces. Nested sub-agent responses are now neatly tucked under clean, clickable accordion elements. | Prevents chat stream clutter; dramatic readability improvement during complex workflows. | History remains uneditable; delegation headers lack active loading indicator cues. |
| **1.2** | Per-agent personality customizer modal, offering fine-grained adjustments to system prompts on the fly. | Real-time agent behavioral tweaking without modification of local source code. | System instructions apply globally across all chats instead of mapping to isolated streams. |
| **1.3** | Native `@-mentions` and an interactive manual delegation dropdown menu built directly into the main prompt bar. | Highly predictable routing; bypasses strict reliance on LLM structure parsing triggers. | Legacy structural syntax commands are still monitored, risking accidental double-routing. |
| **1.4** | Multi-chat session capabilities per agent combined with automated key-value global user profiling profiles. | Contextual longevity; organized multi-topic isolation; global knowledge sharing across agents. | Profile extraction lacks explicit data tuning controls; vulnerable to hallucinated memory flags. |
| **1.5** | Comprehensive user message mutation (pencil icon) supporting complete downstream thread generation. Added chat session rename/delete actions. | Infinite historic branching control; smooth typo correction and prompt optimization workflows. | Assistant-generated bubbles cannot be manually altered; network interruptions halt re-generation. |
| **2.0** | Standalone Dolphin Uncensored client built over **AI Horde** API infrastructure. Operates bypass-ready without configuration. | Pure unfiltered output context; zero operational keys or backend setups needed to deploy. | Polling overhead limits speed; high queuing dependency risks; lacks core agent matrix dynamics. |

---

## 🔍 Detailed Component Breakdowns

### 🔴 Version 1.0 – Core Architecture
*Artifact Snapshots: `00fa84`, `091104`, `2065d4`, `3d696b`, `4d171c`, `525cf7`, `53162f`, `580778`, `6bf8a0`, `8c53a1`, `e9cc44`, `f2a302`*

*   **Pre-configured Personas:** ships with **Dolphin** (creative operations) and **Debugger** (code optimization).
*   **Rich Text Processing:** complete markdown rendering parsing coupled with standard syntax highlighting blocks.
*   **Encapsulated Logic:** routes deep trace outputs safely inside `<thinking>` tags to preserve visual balance.
*   **Autonomous Routing:** uses `[DELEGATE: agent_name: task]` and `[RETRIEVE: agent_name: query]` hooks.

---

### 🟡 Version 1.1 – Structural Cleaning
*Artifact Snapshot: `778489`*

*   **Clean Accordion Views:** isolates deep processing steps into clean `.delegation-header` class brackets.
*   **Scroll Optimization:** prevents text explosions, keeping active conversation tracking focused.

---

### 🟡 Version 1.2 – Behavioral Overrides
*Artifact Snapshot: `a2c28a`*

*   **Prompt Injectors:** introduces modal configurations to dynamically append instructions (e.g., *"Respond exclusively in JSON"*).
*   **Ad-Hoc Testing:** fast-tracks target testing for specialized prompt engineering vectors.

---

### 🟡 Version 1.3 – Intended Routing Hooks
*Artifact Snapshot: `a96a23`*

*   **Target Mentions:** users can prefix standard text prompts with `@AgentName` to bypass automation layers entirely.
*   **Drop Elements:** select destination pathways explicitly using a responsive interface control menu.

---

### 🟡 Version 1.4 – Parallel Workspace Engine
*Artifact Snapshots: `716dd5`, `fcd8f6`*

*   **Isolated Workspace Contexts:** spin up separate chat streams under individual agents without cross-talk.
*   **Background Profiling:** continuously extracts background facts to build a persistent memory structure.

---

### 🟢 Version 1.5 – Master Node Optimization *(Recommended Standard)*
*Artifact Snapshot: `feceb6`*

*   **Inline Editing Controls:** hover over sent blocks to update past prompts; cleanly updates downstream history.
*   **Node Integrity Controls:** native confirmation screens prevent accidental workspace losses.

---

### 🔵 Version 2.0 – Dolphin Uncensored Branch
*Artifact Snapshots: `68920c`, `a189ea`, `fdaef0`*

*   **Peer Network Engine:** relies entirely on distributed node generation layers (`stablehorde.net`).
*   **ChatML Conformity:** tailored prompt assembly structures lock in strict uncensored text output responses.

---

## ⚙️ Execution and Operations Guide

### 1. Multi‑Agent Studio Environments (`v1.x`)
1. Open any targeted file pathway in `versions/1.x/*.html` inside a standard modern browser window.
2. Provide your custom credentials via the **Settings/API** modal menu located in the top panel.
3. Chat naturally, tag specific personas using `@AgentName`, or allow the automated framework to delegate tasks dynamically.

### 2. Dolphin Uncensored Sandbox (`v2.0`)
1. Run any selection under `versions/2.0/*.html` inside your browser.
2. Monitor terminal messages until the system displays a `Ready` status flag.
3. Submit prompts directly. *Note: Response intervals fluctuate between 10–30 seconds based on live network queue loads.*

---

## 🛠️ Technical Specifications

*   **Security Contexts:** Multi-agent instances route calls directly to `api.groq.com`. For public deployments, extract your API keys entirely.
*   **Storage Profiles:** Application configurations, conversational history trees, and extracted context objects rely 100% on `localStorage`. Flushing browser storage indices resets the canvas state completely.
*   **CORS Compliance:** Architecture calls target endpoints strictly client-side—no internal proxy servers required.

---

## 🚀 Roadmap and Backlog

* [ ] Direct editing of assistant-generated message blocks.
* [ ] Full-text search and filtering across deep historical chat paths.
* [ ] Portable JSON schema data engines (Complete Export/Import loops).
* [ ] Dynamic streaming mechanisms handling inter-agent delegation pipelines.

---

> ℹ️ *Note: Compiled across 23 historical configuration snapshots. Production multi-agent use-cases should utilize **v1.5**; baseline unfiltered tests should run over **v2.0**.*
