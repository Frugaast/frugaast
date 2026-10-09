<div align="center">
  <h1>Frugaast 🧠🛠️</h1>
  <p><b>A frugal, 1-pass, agentless coding assistant that keeps <em>you</em> in control.</b></p>

  <p>
    <a href="#why-frugaast">Why Frugaast?</a> •
    <a href="#core-features">Features</a> •
    <a href="#how-it-works">How it Works</a> •
    <a href="#getting-started">Getting Started</a>
  </p>
</div>

---

**Coding with AI agents feels fast—until you actually run the code.** 

If you're exhausted by complex "agentic" workflows, endless autonomous loops that write bloated code, and the terrifying realization that you no longer understand your own codebase, Frugaast is for you.

Frugaast is a desktop coding assistant built on a simple philosophy: **The developer is the driver; the AI is just the engine.** 

No autonomous agents. No invisible context gathering. Just transparent, deterministic, 1-pass AI assistance that integrates deeply with your local and remote (SSH) Git workspaces.

## 🛑 The Problem with Agentic AI

Developers are increasingly frustrated with the current state of AI coding agents. We built Frugaast to solve the core pain points of the modern AI workflow:

| The Agentic Nightmare | The Frugaast Solution |
| :--- | :--- |
| **Loss of Mental Model:** Agents write hundreds of lines you didn't ask for. Suddenly, no one understands how the system works. | **Developer-Driven:** You explicitly build the prompt context (files, symbols). You know exactly what the AI knows. |
| **Poor Code Quality & Bloat:** Agents make up endpoints, ignore existing libraries, and write "plausible bullshit." | **1-Pass Deterministic Edits:** Frugaast uses explicit SEARCH/REPLACE edits. 1 prompt = 1 action. No spiraling autonomous loops. |
| **Increased Workload:** Reviewing verbose, confident-but-wrong AI slop takes longer than just writing it yourself. | **Fast Reverts & Git Native:** One-click `Undo` for bad AI edits. All changes are staged and reviewed in a native Git diff viewer. |
| **Complex Agent Setups:** Orchestrating multi-agent frameworks is a chore. | **Zero Friction:** A lightweight desktop app. Point it at a local repo or connect via SSH. Bring your own API key. |

---

## ✨ Core Features

### 🎯 1-Pass, Transparent Execution
- **Ask Mode:** Ask questions without risking unwanted code changes.
- **Code Mode:** Apply targeted SEARCH/REPLACE edits. Changes are applied and committed to your local or remote repository instantly.
- **Instant Undo:** AI hallucinated? Hit `Undo` right in the chat to revert the commit.
- **Prompt Preview:** See the *exact* raw JSON prompt (System + User context) before spending a single token. No hidden magic.

### 🧩 Laser-Focused Context Builder
Stop letting the AI guess what matters. Build your context explicitly:
- **Left Sidebar Explorer:** Add specific files or entire folders to the context with a click.
- **Symbol-Driven Context (Extend):** Search and add specific classes, methods, or definitions from your Repo Map without loading thousands of lines of irrelevant code.
- **Optional Overrides:** Pin static reference files (like `ARCHITECTURE.md`), toggle the Workspace Tree, or adjust the Repo Map token budget dynamically.

### 🌐 First-Class SSH Remote Workspaces
Code on a remote server as seamlessly as on your local machine.
- Connect to named SSH hosts effortlessly.
- Frugaast auto-installs a lightweight, offline repository helper on the remote host (requires no remote Python, pip, or sudo).
- The AI runs locally, keeping your API keys safe on your desktop, while file reads and Git commits happen directly on the remote server.

### 💸 Built for Frugality (BYOK)
- Bring your own API keys (OpenAI, Anthropic, Gemini, or local via LiteLLM).
- **Cost Tracking:** Native dashboard tracking token usage, cost per session, and response times. Know exactly how much your AI assistance costs.
- **Web Chatbot Mode:** Want to use Claude.ai or ChatGPT's web UI to save API costs? Frugaast lets you copy your highly-curated workspace context, ask for changes in the browser, paste the response back, and auto-apply the edits.

---

## 🛠️ How it Works

Frugaast uses a fast **React/Tauri desktop GUI** coupled with a self-contained **Python sidecar** via WebSockets.

### The UI Layout
```text
┌ Title bar: SSH hosts · workspaces · settings (API Keys, Models, Theme)
├ Workspace tabs (e.g., frontend-repo, backend-repo @ dev-server)
├──────────────┬──────────────────────────────┬──────────────┐
│ Left sidebar │ View tabs:                   │ Right        │
│  Explorer /  │ 💬 Assistant                 │ sidebar:     │
│  Search /    │ 🌐 Web Chatbot               │ 📜 Chat      │
│  Extend      │ 💰 Costs                     │    History   │
│ ──────────── │ 🔍 Code Explore              │ 🌿 Git       │
│ Prompt       │ 📄 Files / Diffs             │    History   │
│ Builder      │                              │              │
└──────────────┴──────────────────────────────┴──────────────┘
```

### The Workflow
1. **Open a Workspace:** Select a local Git repository or connect to a remote host via SSH.
2. **Build Context:** Click `+` on files in the Explorer, or use **Extend** to inject specific symbols into the prompt.
3. **Ask or Code:** Type your request. (Use `` ` `` for intelligent symbol autocomplete).
4. **Review & Iterate:** If in Code mode, Frugaast edits your code and creates a Git commit. Review it in the Git History tab, or hit `Undo` if the AI missed the mark.


## 🚀 Getting Started

*(Installation instructions coming soon - check the [Releases](https://github.com/Frugaast/frugaast/releases) page for macOS, Windows, and Linux binaries).*

1. Download and install Frugaast.
2. Open **Settings (Gear Icon) > API Keys** and add your provider keys (e.g., `ANTHROPIC_API_KEY`).
3. Open a local Git repository or connect to an SSH host.
4. Add files to your context and start coding.

---

## ⚖️ License & Privacy

Frugaast is a desktop-first application. Your API keys, chat history, repository maps, and settings are stored locally on your machine (or securely via SSH tunnel for remote workspaces). We do not collect your code. 

Free usage allows up to 3 open workspaces simultaneously. See our [pricing / license](https://frugaast.dev/pricing) page for Pro features.

---
*Reclaim your mental model. Ditch the autonomous bloat. Code with Frugaast.*
