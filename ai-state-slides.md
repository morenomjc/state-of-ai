---
marp: true
theme: default
paginate: true
style: |
  section {
    font-family: 'Segoe UI', Arial, sans-serif;
    background: #0f1117;
    color: #e8e8f0;
  }
  h1 { color: #a78bfa; font-size: 2rem; margin: 0 0 0.3em; }
  h2 { color: #7dd3fc; font-size: 1.5rem; border-bottom: 2px solid #7dd3fc22; padding-bottom: 0.2em; margin: 0 0 0.4em; }
  h3 { color: #86efac; margin: 0.4em 0 0.2em; }
  a { color: #f9a8d4; }
  strong { color: #fcd34d; }
  table { border-collapse: collapse; width: 100%; font-size: 0.82rem; }
  th { background: #1e293b; color: #7dd3fc; padding: 5px 12px; text-align: left; }
  td { padding: 4px 12px; border-bottom: 1px solid #334155; color: #e2e8f0; background: #161b27; }
  tr:nth-child(even) td { background: #1a2235; }
  ul, ol { line-height: 1.55; margin: 0.2em 0; }
  li { margin-bottom: 0; }
  p { margin: 0.3em 0; }
  .lead { font-size: 1.2rem; color: #94a3b8; }
  section.title h1 { font-size: 2.8rem; text-align: center; margin-top: 1rem; }
  section.title h2 { text-align: center; border-bottom: none; color: #94a3b8; font-size: 1.4rem; margin-top: 0.2rem; }
  section.title p  { text-align: center; color: #94a3b8; }
  code { background: #1e293b; color: #86efac; padding: 0.1em 0.4em; border-radius: 4px; font-size: 0.9em; }
  pre { background: #1e293b; border: 1px solid #334155; border-radius: 8px; padding: 0.6em 0.8em; margin: 0.4em 0; }
  pre code { background: none; padding: 0; color: #e2e8f0; font-size: 0.82rem; }
  blockquote { border-left: 4px solid #7dd3fc; background: #1e293b; margin: 0.4em 0; padding: 0.4em 0.8em; color: #cbd5e1; font-style: italic; border-radius: 0 6px 6px 0; }
  blockquote p { margin: 0; }
---

<!-- _class: title -->

# The State of AI
## April 2026

A snapshot of where we are, how we got here,
and where things are heading.

---

## Agenda

1. Brief History of AI
2. Types of AI
3. Large Language Models — Models & Vendors
4. Agents, Skills & MCP
5. Coding Agents
6. Autonomous Agents — OpenClaw
7. Key Takeaways

---

## A Brief History of AI

| Year | Milestone |
|------|-----------|
| 1950 | Turing Test — *"Can machines think?"* |
| 1980s | Expert systems; first AI winters |
| 2012 | Deep learning — AlexNet wins ImageNet |
| 2017 | **Transformer** architecture invented |
| 2020 | GPT-3 — few-shot learning at scale |
| 2022 | **ChatGPT** — 100 M users in 60 days |
| 2023 | GPT-4, Claude, Gemini go mainstream |
| 2024 | Reasoning models, open-source Llama 3 |
| **2025–26** | **Agentic AI, coding agents, autonomous bots** |

---

## Types of AI — The Landscape

```
Narrow AI          → one task (spam filter, chess engine)
       ↓
Generative AI      → creates text, images, audio, video, code
       ↓
Multimodal AI      → combines text + image + audio in one model
       ↓
Reasoning AI       → thinks step-by-step before answering
       ↓
Agentic AI         → plans + executes multi-step goals autonomously
       ↓
Embodied / Robotic → AI in the physical world
```

> We are living through the transition from **Generative → Agentic AI**

---

## Generative AI — What It Can Create

| Modality | Examples |
|----------|----------|
| **Text** | Articles, code, summaries, emails |
| **Images** | DALL·E 3, Midjourney, Stable Diffusion |
| **Audio** | Voice cloning, music generation |
| **Video** | Sora, Runway, Kling |
| **Code** | GitHub Copilot, Claude Code, Cursor |
| **3D / Data** | Protein folding (AlphaFold), CAD |

Powered by **large neural networks** trained on billions of examples.

---

## Large Language Models (LLMs)

An LLM is a neural network trained to **predict the next token** across massive text corpora.

**Why they're powerful:**
- Emergent abilities at scale — reasoning, translation, coding without explicit training
- In-context learning — adapt to new tasks from a few examples in the prompt
- Instruction following — respond to natural language commands

**Key metrics:**
- **Context window** — how much text the model can "see" at once
- **Parameters** — billions of learned weights (size ≠ quality, but matters)
- **Benchmarks** — MMLU, HumanEval, MATH, GPQA

---

## Models & Vendors — 2026 Snapshot

| Vendor | Model | Strength |
|--------|-------|----------|
| **Anthropic** | Claude 4 Opus / Sonnet / Haiku | Reasoning, coding, safety |
| **OpenAI** | GPT-4o, o3/o4, GPT-5 | Breadth, multimodal, ecosystem |
| **Google** | Gemini 2.5 / 3 Pro | 1M token context, search integration |
| **Meta** | Llama 4 Scout | **Open-source**, 10M tokens, free |
| **Mistral** | Mistral Large 2 | European, efficient, open weights |
| **DeepSeek** | DeepSeek R1 / V3 | Competitive reasoning, low cost |

> **500+** models available today. Open-source is closing the gap with frontier models.

---

## What Is an AI Agent?

A **chatbot** answers one question at a time.
An **agent** pursues a goal across many steps.

```
Goal → Plan → Act → Observe → Reflect → Act → ... → Done
```

**Agents need:**
- **Memory** — context window + long-term storage
- **Tools** — search, code execution, file I/O, APIs
- **Planning** — break goals into subtasks, self-correct
- **Skills** — reusable packaged behaviours

> *"Move from reactive Q&A to proactive, autonomous execution"*

---

## Skills & MCP — The Connective Tissue

### Skills
Pre-packaged, reusable agent behaviours.
Think browser extensions for AI agents.
Examples: `/review`, `/gsd-plan-phase`, `/debug`

### Model Context Protocol (MCP)
Open standard — the **"USB-C for AI"**

- Connects any model to external tools via a standardised interface
- 200+ community servers: GitHub, Slack, PostgreSQL, Stripe, Docker, Figma…
- Donated to the **Linux Foundation** (Dec 2025) — now vendor-neutral

> MCP + Skills = agents that can do real work in your actual systems

---

## Coding Agents — AI That Writes Software

Beyond autocomplete → agents that **read, plan, write, test, and commit** code.

| Agent | Maker | Key Feature |
|-------|-------|-------------|
| **Claude Code** | Anthropic | CLI + IDE; full repo context; multi-agent |
| **Copilot Workspace** | GitHub | PR-centric plan → edit → test flow |
| **Cursor** | Anysphere | Editor built around AI context |
| **Devin** | Cognition | Fully autonomous dev environment |
| **OpenHands** | All-Hands AI | Open-source Devin alternative |

Coding agents are **software engineering problems**, not just model problems —
~98% of the system is infrastructure, only ~1.6% is AI decision logic.

---

## Claude Code — Deep Dive

**What it does:**
- Reads your **entire codebase** in seconds
- Plans changes across multiple files
- Runs tests, iterates on failures, commits code
- Supports **multi-agent orchestration** — parallel agents on sub-tasks

**How it connects:**
- CLI, VS Code, JetBrains IDE extensions
- **MCP servers** for external tools
- **Hooks** — custom shell commands on agent events
- **Agent SDK** — build your own agents on top of Claude Code

> *"The first AI system that feels like a junior dev, not an autocomplete engine"*

---

## Autonomous Agents — OpenClaw

**What is it?**
Free, open-source, **self-hosted** AI agent that runs on your machine and operates via consumer messaging apps (Signal, Telegram, Discord, WhatsApp).

**Timeline:**
- Nov 2025 — launched as "Clawdbot" by Peter Steinberger (Austria)
- Jan 2026 — renamed **OpenClaw**; fastest-growing GitHub repo ever
- Feb 2026 — creator joins OpenAI; non-profit foundation for stewardship
- Mar 2026 — restricted by Chinese government over security concerns

**Why it matters:**
- Model-agnostic (Claude, GPT-4o, DeepSeek, Llama)
- Privacy-first — your data stays local
- Extensible via `skill.md` files — community-driven
- Signals a shift: AI agents as **personal, locally-owned** systems

---

## The Bigger Picture — Trends to Watch

**Now (2026):**
- 65% of global organisations use generative AI (McKinsey)
- AI in healthcare diagnosis, credit review, algorithmic trading
- Personal AI assistants becoming the default digital interface

**Near future:**
- Multi-agent systems where AI agents hire other AI agents
- AI with persistent memory across months and years
- Regulation catching up — EU AI Act, US executive orders

**The hard questions:**
- Who owns AI-generated work?
- How do we verify AI output is trustworthy?
- What happens to knowledge work at scale?

---

## Key Takeaways

1. AI shifted from **chatbot → autonomous agent** in ~3 years
2. **Open-source models** (Llama 4, DeepSeek) now rival frontier models
3. **MCP** is becoming the universal connector for AI ↔ tools
4. **Coding agents** (Claude Code, Devin) are entering daily dev workflows
5. **Autonomous agents** (OpenClaw) bring AI to personal, local automation
6. The key skill is no longer "how to use AI" but **"how to direct AI agents"**

---

<!-- _class: title -->

# Thank You

**Resources**
- [claude.ai/code](https://claude.ai/product/claude-code) — Claude Code
- [openclaw.ai](https://openclaw.ai) — OpenClaw autonomous agent
- [modelcontextprotocol.io](https://modelcontextprotocol.io) — MCP standard
- [llm-stats.com](https://llm-stats.com/ai-trends) — LLM benchmarks & trends

*Presentation generated April 28, 2026*
