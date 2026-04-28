---
marp: true
theme: default
paginate: true
style: |
  section {
    font-family: 'JetBrains Mono', 'Fira Code', monospace;
    font-size: 1.2rem;
    background: #0d1117;
    color: #c9d1d9;
    padding: 50px 70px;
  }
  h1 { color: #79c0ff; font-size: 2rem; margin-bottom: 0.3em; }
  h2 { color: #56d364; font-size: 1.5rem; border-bottom: 1px solid #30363d; padding-bottom: 0.2em; margin-bottom: 0.5em; }
  h3 { color: #ffa657; font-size: 1.1rem; margin-bottom: 0.2em; }
  strong { color: #ffa657; }
  em { color: #a5d6ff; }
  a { color: #d2a8ff; }
  code { background: #161b22; color: #79c0ff; padding: 2px 6px; border-radius: 4px; font-size: 0.95em; }
  pre { background: #161b22; padding: 0.8em 1em; border-radius: 6px; border: 1px solid #30363d; font-size: 0.88rem; }
  blockquote { border-left: 3px solid #56d364; padding-left: 0.8em; color: #8b949e; margin-top: 0.8em; }
  ul { line-height: 1.9; margin-top: 0.3em; }
  li { margin-bottom: 0.1em; }
  table { border-collapse: collapse; width: 100%; font-size: 0.85rem; }
  th { background: #161b22 !important; color: #56d364 !important; padding: 6px 12px; border: 1px solid #30363d; text-align: left; }
  td { background: #0d1117 !important; color: #c9d1d9 !important; padding: 5px 12px; border: 1px solid #21262d; }
  tr:nth-child(even) td { background: #111820 !important; }
  section.title { display: flex; flex-direction: column; justify-content: center; text-align: left; }
  section.title h1 { font-size: 2.6rem; color: #79c0ff; }
  section.title p { color: #8b949e; }
---

<!-- _class: title -->

# The State of AI
## April 2026 — Technical Overview

Architecture, models, agents, MCP, and coding systems

---

## Timeline — From Transformer to Agents

| Year | Event |
|------|-------|
| 2017 | "Attention Is All You Need" — Transformer born |
| 2020 | GPT-3: 175B params, emergent few-shot learning |
| 2022 | RLHF fine-tuning → ChatGPT; instruction following at scale |
| 2023 | GPT-4 multimodal; Claude, Gemini enter; open-source Llama 1/2 |
| 2024 | Chain-of-thought reasoning (o1); Llama 3; function calling matures |
| 2025 | Coding agents ship (Claude Code, Devin); MCP standardised |
| 2026 | Multi-agent orchestration; autonomous local agents (OpenClaw) |

---

## Types of AI Systems

- **Narrow AI** — single-task discriminative models (classifiers, detectors)
- **Generative AI** — autoregressive LLMs, diffusion models, audio/video
- **Multimodal** — unified embedding space across text, image, audio, video
- **Reasoning** — extended chain-of-thought at inference time (o3, R1)
- **Agentic** — tool-using, multi-step planning, self-correcting loops
- **Embodied** — physical robots; Vision-Language-Action models (RT-2, π0)

---

## How LLMs Work — In Brief

- Transformer trained on next-token prediction over trillions of tokens
- Instruction-tuned via **RLHF** or **DPO** for helpful responses
- Key hyperparameters: **context window**, **parameter count**, **temperature**
- Emergent capabilities appear at scale — not explicitly trained

**Evaluation axes:**
- Reasoning: MATH, GPQA, ARC-AGI
- Coding: HumanEval, SWE-bench
- Knowledge: MMLU, HELM

---

## RAG — Retrieval-Augmented Generation

Solves LLM limitations: stale training data, hallucination on private knowledge, context limits.

**Pipeline:**
```
Query → Embed → Vector Search → Top-K Chunks → Prompt + Context → LLM → Answer
```

**Key components:**
- **Chunking** — split docs into retrievable units (size matters)
- **Embeddings** — semantic vector representation (OpenAI, Cohere, `nomic-embed`)
- **Vector DB** — Pinecone, Weaviate, pgvector, Chroma, Qdrant
- **Reranking** — re-score retrieved chunks for relevance (Cohere Rerank, cross-encoders)

**Advanced patterns:** HyDE, multi-hop RAG, agentic RAG (agent decides *when* to retrieve)

---

## Models & Vendors — 2026

| Vendor | Model | Context | Notes |
|--------|-------|---------|-------|
| Anthropic | Claude 4 Opus/Sonnet/Haiku | 200K | Strong reasoning & coding |
| OpenAI | GPT-4o, o3/o4, GPT-5 | 128K–1M | Multimodal, widest ecosystem |
| Google | Gemini 2.5 / 3 Pro | 1M | Grounding + Search integration |
| Meta | Llama 4 Scout | **10M** | Open weights, commercial OK |
| DeepSeek | R1 / V3 | 128K | Open-weight, strong at math/code |
| Mistral | Large 2 | 128K | European, open, efficient MoE |

> 500+ models in total. Open-source now rivals closed on most benchmarks.

---

## AI Agent Architecture

```
┌─────────────────────────────────────────────┐
│                   Agent Loop                │
│                                             │
│  Goal → Planner → Action → Observation      │
│             ↑__________________________|    │
└─────────────────────────────────────────────┘
         ↓              ↓             ↓
      Memory          Tools        Skills
   (ctx + vector)  (APIs, shell)  (packaged behaviours)
```

- **Memory**: in-context + RAG vector store + episodic files
- **Tools**: function-calling, code interpreter, browser, shell
- **Planning**: ReAct, Tree-of-Thoughts, LLM-as-orchestrator

---

## Model Context Protocol (MCP)

Open standard — the **"USB-C for AI tools"**
Donated to Linux Foundation / AAIF — Dec 2025

**Architecture:**
- **Tools** — callable functions with JSON schemas
- **Resources** — readable data (files, DB tables, API endpoints)
- **Prompts** — reusable instruction templates
- Transport: `stdio` (local) or `HTTP/SSE` (remote)

**Ecosystem:** 200+ servers — GitHub, Slack, Postgres, Stripe, Docker, Figma, Kubernetes…

---

## Skills — Packaged Agent Behaviours

Skills are pre-built, reusable agent workflows invoked by slash command.

```
/review           → code review pipeline
/gsd-plan-phase   → multi-step planning agent
/debug            → scientific debugging loop
/security-review  → threat model analysis
```

- Defined as markdown instruction files (`skill.md`)
- Composable — skills can invoke other skills
- OpenClaw popularised community skill sharing at scale

---

## Coding Agents — Landscape

| Agent | Model | Approach |
|-------|-------|----------|
| **Claude Code** | Claude 4 | CLI + IDE; full repo; multi-agent; hooks; MCP |
| **Copilot Workspace** | GPT-4o | PR-centric; diff-based plan → edit → CI |
| **Cursor** | Claude/GPT | Editor-native; inline + composer modes |
| **Devin** | Proprietary | Sandboxed VM; long-horizon autonomous tasks |
| **OpenHands** | Any | Open-source; Docker-sandboxed; tool-use heavy |

> Research: ~1.6% of system is AI logic; ~98.4% is operational infrastructure

---

## Claude Code — Architecture

**Execution model:**
- Maps full repo via agentic search (no manual context selection)
- Plans → edits files → runs shell/tests → iterates on failure → commits

**Extension points:**
- `MCP servers` — plug in any external tool
- `Hooks` — shell commands on pre/post tool events
- `Agent SDK` — build custom agents on Claude Code's tool layer
- `CLAUDE.md` — project-level persistent instructions

**Multi-agent:** lead agent spawns sub-agents for parallel workstreams

---

## OpenClaw — Autonomous Local Agent

**What it is:** self-hosted, model-agnostic autonomous agent
**Interface:** consumer messaging (Signal, Telegram, Discord, WhatsApp)
**Model support:** Claude, GPT-4o, DeepSeek, Llama (any OpenAI-compatible endpoint)

**Key design decisions:**
- Runs locally — data never leaves your machine
- `skill.md` files = community-extensible capability system
- Event-driven loop: message → plan → act → respond

**Timeline:** Nov 2025 (Clawdbot) → Jan 2026 (OpenClaw) → fastest-growing GitHub repo ever

---

## Trends & Open Problems

**Capability frontier:**
- Long-horizon task completion (hours, not minutes)
- Multi-agent coordination and trust between agents
- Persistent memory and personalisation over time

**Infrastructure:**
- MCP as universal tool layer — replacing bespoke integrations
- Speculative execution, prompt caching, distillation for cost

**Open problems:**
- Hallucination under distribution shift
- Reliable agent termination and sandboxing
- Eval frameworks that track real-world task success

---

## Key Takeaways

1. **Transformer → Agent** is the defining architectural shift of this decade
2. Open-source models (Llama 4, DeepSeek) now competitive with frontier closed models
3. **MCP** is becoming the standard interface for AI ↔ external systems
4. Coding agents are production-grade — not just autocomplete
5. **OpenClaw** proves locally-owned autonomous agents are viable at consumer scale
6. The bottleneck is now **orchestration and evals**, not raw model capability

---

<!-- _class: title -->

# Thank You

**Docs & References**
- [code.claude.com/docs](https://code.claude.com/docs) — Claude Code
- [modelcontextprotocol.io](https://modelcontextprotocol.io) — MCP spec
- [openclaw.ai](https://openclaw.ai) — OpenClaw
- [arxiv.org/abs/2604.14228](https://arxiv.org/abs/2604.14228) — *Dive into Claude Code*
- [llm-stats.com](https://llm-stats.com/ai-trends) — model benchmarks

*April 28, 2026*
