# Athena · Multi‑Agent AI Studio

A browser‑based, fully client‑side multi‑agent system that lets you create, customise, and orchestrate multiple AI agents (powered by Groq’s Llama 3.3‑70B) with persistent conversations, delegation, memory, message editing, and collapsible reasoning.
**Also includes a separate branch:** **Dolphin Uncensored** – a single‑agent chat using the AI Horde (uncensored Dolphin models).

## ⚠️ Note ⚠️
All historical releases contain a revoked API key. To use them, replace "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" with your own Groq key. Get one free at console.groq.com.

<img width="1919" height="998" alt="image" src="https://github.com/user-attachments/assets/88b2c32a-ca25-497f-b550-d57a2ff13258" />
---

## Version History

| Version | Improve
ements | Advantages | Disadvantages |
|---------|--------------|------------|----------------|
| **1.0** | Initial multi‑agent system with basic delegation (`[DELEGATE:agent:task]`) and retrieval (`[RETRIEVE:agent:query]`). Streaming responses with `<thinking>` tags. Sidebar with agent list and per‑agent chat sessions. LocalStorage persistence. | Functional foundation; agents can delegate work to each other; code copy buttons; collapsible thinking blocks. | No message editing; no 3‑dot chat menus; delegation sometimes fails to include full code; no custom agent preferences. |
| **1.1** | Collapsible delegation responses – delegated replies are hidden under a clickable header. | Cleaner chat UI; long delegated responses don’t clutter the view. | Still no way to edit or delete individual messages. |
| **1.2** | Editable agent personalities – each agent gets a custom system prompt and a toggleable “preferences” modal. | Agents can be fine‑tuned on the fly; user‑defined instructions. | Preferences are global per agent, not per chat. |
| **1.3** | @‑mentions and manual delegation dropdown. You can now type `@Debugger` to delegate directly. | More intuitive delegation; works without relying on the AI to output `[DELEGATE:...]`. | Delegation still lacks a confirmation step. |
| **1.4** | Multiple chat sessions per agent + shared user memory. Each agent can have several independent conversations; memory (user profile) is extracted automatically from conversations. | Persistent context across chats; agents remember facts about the user. | Memory extraction is basic (key‑value only); no way to edit memory manually. |
| **1.5** | **Message editing** (pencil icon on user messages) and **3‑dot menus** for chat sessions (rename/delete). Full regeneration after edit. | Complete control over conversation history; edit any user message and the assistant will re‑answer. | Editing does not allow editing assistant messages; no undo for regenerations. |
| **2.0** | **Dolphin Uncensored** – standalone single‑agent chat using AI Horde (stablehorde.net). No registration, no API key. Supports markdown, code highlighting, copy button, and animated typing indicator. | Truly uncensored; works without any backend; easy to deploy. | Slower (polling based); may time out if Horde workers are busy; no agent delegation. |

---

## Detailed Version Breakdown

### Version 1.0 – Foundation
*Files: `00fa84`, `091104`, `2065d4`, `3d696b`, `4d171c`, `525cf7`, `53162f`, `580778`, `6bf8a0`, `6bf8a0 (1)`, `8c53a1`, `e9cc44`, `f2a302`*

**Improvements (over nothing):**
- Two default agents: Dolphin (creative) and Debugger (code expert)
- Chat interface with user/assistant bubbles, markdown rendering, syntax highlighting
- Agents can output `<thinking>…</thinking>` (hidden until clicked)
- Delegation via `[DELEGATE: agent_name: task]` and retrieval via `[RETRIEVE: agent_name: query]`
- LocalStorage saves all agents, chats, and user memory
- Code copy button on every code block

**Advantages:** Fully functional multi‑agent system in a single HTML file; works offline after first load.

**Disadvantages:** No way to edit past messages; chat sessions cannot be renamed or deleted; delegation often fails to include the full code (only a placeholder).

---

### Version 1.1 – Collapsible Delegation
*File: `778489`*

**Improvements:**
- Delegated responses are wrapped in a `<div class="delegation-header">` that can be expanded/collapsed.
- The chat stays clean; long answers from target agents are hidden by default.

**Advantages:** Better UX when delegating complex tasks.

**Disadvantages:** Still no message editing; delegation header does not show a loading state.

---

### Version 1.2 – Editable Personalities
*File: `a2c28a`*

**Improvements:**
- Each agent has a “Preferences” button (sliders icon) that opens a modal.
- You can enable custom behaviour and write a custom system prompt (e.g., “act sarcastic”).
- The custom prompt is appended to the base system prompt.

**Advantages:** Agents can be tailored on the fly without editing code.

**Disadvantages:** Custom instructions are global for the agent (affects all chats); no way to reset to default.

---

### Version 1.3 – @Mentions + Manual Delegation
*File: `a96a23`*

**Improvements:**
- Type `@AgentName` in the input to delegate to that agent.
- A dropdown in the input area lets you select a target agent manually.
- The current agent no longer needs to output a `[DELEGATE:...]` command – the UI handles it directly.

**Advantages:** Much more reliable delegation; works with any agent name.

**Disadvantages:** The AI’s own delegation commands are still recognised, leading to potential double delegation.

---

### Version 1.4 – Multiple Chats + Shared Memory
*Files: `716dd5`, `fcd8f6`*

**Improvements:**
- Each agent can have multiple named chat sessions (create, rename, delete).
- A “User profile” panel shows extracted facts (name, preferences, etc.) from conversations.
- Memory is shared across all agents and chats (global user memory).

**Advantages:** Long‑term context; organised conversations; memory persists.

**Disadvantages:** Memory extraction is not editable and may produce incorrect facts; no way to delete specific memories.

---

### Version 1.5 – Edit Messages + 3‑dot Menus
*File: `feceb6`*

**Improvements:**
- **Edit user messages**: a pencil icon appears on hover; clicking replaces the bubble with a textarea. After saving, the conversation is truncated after that message and the assistant re‑answers.
- **3‑dot menus** next to each chat session allow rename/delete.
- Confirmation modals for destructive actions (delete agent, delete chat, clear chat).

**Advantages:** Full conversational control; users can fix typos or re‑ask questions without losing context.

**Disadvantages:** Assistant messages cannot be edited; regenerating after an edit may fail if the API is busy.

---

### Version 2.0 – Dolphin Uncensored (AI Horde)
*Files: `68920c`, `a189ea`, `fdaef0`, `fdaef0 (1)`*

**Improvements (over no chat):**
- Single‑agent chat using the free, distributed AI Horde (dolphin‑2.2.1‑mistral‑7b / mixtral).
- No API key required; uses `workers: []` to auto‑select available workers.
- Supports markdown, code highlighting, copy button, and animated typing indicator.
- ChatML prompt format with system message enforcing “uncensored” behaviour.

**Advantages:** Truly unrestricted; no registration; works in any modern browser.

**Disadvantages:** Slow (polling every 2 seconds); may time out if Horde is busy; no multi‑agent features.

---

## How to Use

1. **For the Multi‑Agent Studio**: open any `versions/1.x/*.html` file in a browser.  
   - The first time, it will load default agents (Dolphin, Debugger).  
   - Type a message, use `@AgentName` to delegate, or let the AI decide.  
   - Edit past user messages by clicking the pencil icon (v1.5 only).  
   - All data is saved in `localStorage`.

2. **For Dolphin Uncensored**: open any `versions/2.0/*.html` file.  
   - Wait for “ready” status.  
   - Type any question – the model will answer without content filters.  
   - Responses may take 10–30 seconds depending on Horde queue.

---

## Technical Notes

- **API Keys**: The multi‑agent versions use a hardcoded Groq API key (visible in the source). Replace it with your own key if you plan to deploy publicly.
- **CORS**: The multi‑agent versions call `api.groq.com` directly – works in most modern browsers.
- **AI Horde**: The Dolphin versions use `stablehorde.net` – no key needed, but rate‑limited.
- **Storage**: All versions use `localStorage` for agents, chats, and memory. Clearing browser data will reset the app.

---

## Future Ideas (not implemented)

- Edit assistant messages
- Search/filter chat history
- Export/import conversations as JSON
- Per‑chat custom system prompts
- Streaming for delegation (currently waits for full response)

---

*Generated from 23 historical snapshots. The final version (1.5) is recommended for multi‑agent usage; version 2.0 for a simple uncensored chat.*
