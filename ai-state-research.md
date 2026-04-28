# The State of AI — April 2026

## Brief History of AI

| Era | Milestone |
|---|---|
| 1950s | Turing Test proposed; symbolic AI and rule-based reasoning |
| 1980s | Expert systems; AI winters from unmet expectations |
| 2012 | Deep learning breakthrough — AlexNet wins ImageNet |
| 2017 | Transformer architecture ("Attention Is All You Need") |
| 2020 | GPT-3 shows emergent few-shot learning at scale |
| 2022 | ChatGPT launches; 100M users in 60 days |
| 2023 | GPT-4, Claude, Gemini — multimodal and instruction-tuned models go mainstream |
| 2024 | Reasoning models (o1, o3); open-source Llama 3; agentic workflows emerge |
| 2025 | Coding agents (Claude Code, Devin, Copilot Workspace); MCP standard adopted |
| 2026 | Agentic AI mainstream; autonomous local agents (OpenClaw); 65% of orgs using GenAI |

---

## Types of AI

- **Narrow AI** — optimised for a single task (spam filters, chess engines, recommendation systems).
- **Generative AI** — creates new content: text, images, audio, video, code. Powered by large neural networks (LLMs, diffusion models).
- **Multimodal AI** — understands and generates across modalities: text + images + audio + video in one model.
- **Reasoning AI** — produces step-by-step chains of thought before answering, improving accuracy on complex tasks (OpenAI o3, Claude 3.7 Sonnet).
- **Agentic AI** — plans and executes multi-step tasks autonomously using tools, APIs, and feedback loops. Goes beyond single-turn Q&A.
- **Embodied / Robotic AI** — AI controlling physical robots; accelerating in 2025–2026.

---

## LLMs — Models and Vendors (2026)

| Vendor | Model Family | Highlights |
|---|---|---|
| **Anthropic** | Claude 4 (Opus, Sonnet, Haiku) | 200K context, strong reasoning & coding, safety-focused |
| **OpenAI** | GPT-4o, o3/o4, GPT-5 | Multi-modal, long context, leading reasoning benchmarks |
| **Google DeepMind** | Gemini 2.5 / 3 Pro | 1M token context, deep Google ecosystem integration |
| **Meta** | Llama 4 Scout / Maverick | Open weights, 10M token context, free for commercial use |
| **Mistral** | Mistral Large 2 | European, open-weight, efficient instruction-following |
| **DeepSeek** | DeepSeek R1/V3 | Chinese open-source; competitive reasoning at low cost |
| **xAI** | Grok 3 | Real-time X/Twitter data access |

Over 500 models are now publicly available. Key competitive axes: context length, reasoning depth, cost per token, and multimodal capability.

---

## RAG — Retrieval-Augmented Generation

LLMs are static after training — they don't know about recent events or private data. RAG solves this by fetching relevant documents at query time and injecting them into the prompt.

**Pipeline:** `Query → Embed → Vector Search → Top-K Chunks → LLM + Context → Answer`

**Key components:**
- **Chunking** — splitting source documents into retrievable units
- **Embeddings** — semantic vectors that capture meaning (not just keywords)
- **Vector database** — stores and searches embeddings at scale (Pinecone, pgvector, Weaviate, Chroma)
- **Reranking** — second-pass scoring to improve retrieval precision

**Common use cases:** enterprise knowledge bases, customer support bots, legal/medical research assistants, personal document chat.

**Advanced patterns:** HyDE (hypothetical document embeddings), multi-hop RAG, agentic RAG (agent decides when and what to retrieve dynamically).

---

## Agents and Skills

An **AI agent** is a model given a goal, tools, and autonomy to plan and act over multiple steps without per-step human prompting.

**Core components:**
- **Memory** — short-term (context window) + long-term (vector stores, files)
- **Tools** — functions the agent can call: web search, code execution, API calls, file I/O
- **Planning** — decomposing goals into subtasks, sequencing, self-correcting
- **Skills** — pre-packaged, reusable agent behaviours (e.g. `/gsd-plan-phase`, `/review`)

**Model Context Protocol (MCP)** — open standard (donated to the Linux Foundation / AAIF in Dec 2025) that lets any model connect to external systems via a standardised plugin interface. 200+ community servers exist for GitHub, Slack, Postgres, Stripe, Figma, Docker, and more.

Popular agent frameworks: **LangChain**, **LlamaIndex**, **AutoGen**, **CrewAI**, **Anthropic Agent SDK**.

---

## Coding Agents

Coding agents go beyond autocomplete — they read a whole codebase, plan changes across files, run tests, and commit working code.

| Agent | Maker | Style |
|---|---|---|
| **Claude Code** | Anthropic | CLI + IDE; reads full repo; multi-agent orchestration; hooks & MCP |
| **GitHub Copilot Workspace** | Microsoft / GitHub | PR-centric; plans → edits → tests in one flow |
| **Cursor** | Anysphere | Editor built around AI; strong context-aware edits |
| **Devin** | Cognition AI | Fully autonomous; spins up its own dev environment |
| **OpenHands** | All-Hands AI | Open-source Devin alternative |

Recent research shows ~98% of a coding agent's codebase is operational infrastructure, with only ~1.6% being AI decision logic — agents are software engineering problems, not just model problems.

---

## Autonomous Agents — OpenClaw

**OpenClaw** (openclaw.ai) is a free, open-source, self-hosted autonomous AI agent that runs locally and communicates via consumer messaging platforms (Signal, Telegram, Discord, WhatsApp).

- **Origin**: Published Nov 2025 by Austrian developer Peter Steinberger as "Clawdbot"; renamed to OpenClaw in late January 2026.
- **Model-agnostic**: Connects to Claude, GPT-4o, DeepSeek, or any compatible LLM.
- **Viral growth**: One of the fastest-growing GitHub repos ever; sparked a global wave of personal automation bots.
- **Ecosystem**: "Skill files" (`skill.md`) let anyone package and share new agent behaviours — analogous to browser extensions.
- **2026 notes**: Creator joined OpenAI in Feb 2026; non-profit foundation established for stewardship. Restricted by China in March 2026 over security concerns.

OpenClaw represents a broader shift: AI agents moving from cloud SaaS products to locally-owned, privately-run personal automation systems.

---

## Key Takeaways

1. AI has moved from lab curiosity to enterprise infrastructure in ~3 years.
2. The unit of work is shifting from *prompt → answer* to *goal → autonomous execution*.
3. Open-source models (Llama 4, DeepSeek) are closing the gap with frontier closed models.
4. MCP is becoming the "USB-C for AI" — a universal connector for tools and data.
5. Coding agents and autonomous agents (OpenClaw) are putting AI directly in developers' and consumers' workflows.
6. 65% of global organisations use generative AI tools in 2026 (McKinsey).
