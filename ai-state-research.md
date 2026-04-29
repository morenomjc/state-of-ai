# The State of AI - April 2026

## Executive summary

The 2026 AI story is not just "better models." The story is that useful AI is moving up the stack:

- Model quality is still improving, but the real differentiators are context, tool use, reliability, and integration.
- AI is already mainstream inside organizations, but most value is still captured where teams redesign workflows around agents instead of wrapping chat around old processes.
- Open standards and local-first control layers are becoming the connective tissue for agentic systems.

## What changed

| Phase | What changed | Why it matters |
|---|---|---|
| 1950s-2016 | Symbolic AI, expert systems, deep learning | AI was mostly research or narrow automation |
| 2017-2021 | Transformer models and scale | Foundation models became general-purpose infrastructure |
| 2022-2024 | ChatGPT, multimodal models, instruction tuning | AI became a product layer for knowledge work |
| 2025-2026 | Reasoning models, coding agents, MCP, local agents | The unit of value shifts from answers to completed work |

## Useful numbers to keep

- 88% of respondents in McKinsey's 2025 Global Survey say their organizations use AI in at least one business function. [McKinsey](https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai/)
- 71% say their organizations regularly use generative AI in at least one business function. [McKinsey PDF](https://www.mckinsey.com/~/media/mckinsey/business%20functions/quantumblack/our%20insights/the%20state%20of%20ai/2025/the-state-of-ai-how-organizations-are-rewiring-to-capture-value_final.pdf)
- 62% say their organizations are at least experimenting with AI agents. [McKinsey](https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai/)
- 23% say they are already scaling an agentic AI system in at least one function. [McKinsey](https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai/)

## Model landscape

The frontier has not disappeared, but it has become more specialized. The important comparison is no longer just "which model is smartest?" but "which model fits the work?"

| Vendor | Current family | What stands out |
|---|---|---|
| OpenAI | GPT-5.5 / GPT-5.4 / GPT-5 | Latest releases focus on complex work, coding, research, and longer tool-driven tasks. [OpenAI](https://openai.com/research/index/release/) |
| Anthropic | Claude Opus 4.6 / Sonnet 4.6 | Strong coding and reasoning, with 1M token context in beta. [Anthropic](https://www.anthropic.com/news/claude-opus-4-6?id=ClaudeOpus4.6) [Anthropic](https://www.anthropic.com/news/claude-sonnet-4-6?id=19234) |
| Google DeepMind | Gemini 2.5 Pro | Strong coding and multimodal work, with a 1M token context window. [Google DeepMind](https://deepmind.google/technologies/gemini/pro) |
| Meta | Llama 4 Scout / Maverick | Open weights, native multimodality, and a 10M token context window on Scout. [Meta](https://about.fb.com/news/2025/04/llama-4-multimodal-intelligence/) |

## Practical interpretation

The model race now shows up in four dimensions:

1. Context length - can the model see enough of the task?
2. Tool use - can it call the right systems?
3. Reliability - does it complete multi-step tasks without losing the thread?
4. Cost and latency - can it do that work at product speed?

That is why many of the strongest systems are no longer single models. They are model plus orchestration plus retrieval plus permissions plus memory.

## RAG in one sentence

Retrieval-augmented generation is the pattern that gives a model fresh, grounded context at query time instead of relying only on training data.

### Common pipeline

```text
Question -> Embed -> Search -> Top chunks -> Prompt + context -> Answer
```

### Main pieces

- Chunking: split source material into retrievable units.
- Embeddings: convert text into vectors that capture meaning.
- Vector database: store and search those vectors.
- Reranking: improve precision before the model answers.

## Agent layer

An agent is a model wrapped in a loop:

```text
Goal -> Plan -> Act -> Observe -> Revise -> Act -> Done
```

Agents usually need:

- Memory: recent context plus durable state.
- Tools: search, code execution, file I/O, APIs.
- Planning: break the goal into smaller steps.
- Skills: reusable task playbooks.
- Sandboxing: boundaries that keep the system safe when the agent acts.

## MCP

The Model Context Protocol standardizes how applications provide context to models. It is designed around a client-server architecture and exposes tools, resources, and prompts. [MCP docs](https://modelcontextprotocol.io/specification/draft)

Why it matters:

- It reduces one-off integrations.
- It lets agents connect to many tools through a shared interface.
- It makes tool ecosystems more portable across clients and model vendors.

The Linux Foundation announced the Agentic AI Foundation in December 2025 with MCP as one of the founding contributed projects. [Linux Foundation](https://www.linuxfoundation.org/press/linux-foundation-announces-the-formation-of-the-agentic-ai-foundation)

## OpenClaw as a reference point

OpenClaw's docs describe it as a self-hosted assistant you run on your own devices, with support for multiple messaging surfaces and model providers. Its skill system is directory-based and uses `SKILL.md` instruction files. [OpenClaw docs](https://docs.openclaw.ai/index) [OpenClaw skills](https://docs.openclaw.ai/tools/skills)

The useful takeaway is not the branding. It is the pattern:

- The assistant is local-first.
- Skills are packaged behavior.
- The control plane is separated from the model.

## Open questions and risks

- Reliability under long-horizon, multi-step tasks is still the hard problem.
- Tool access increases power, but also increases the need for permissions and auditability.
- Benchmarks are useful, but they do not replace real workflow evaluation.
- Organizations still need to redesign work, not just add AI to existing steps.

## Sources

- [OpenAI Research release index](https://openai.com/research/index/release/)
- [OpenAI GPT-5 announcement](https://openai.com/gpt-5/)
- [Anthropic models overview](https://docs.anthropic.com/en/docs/models-overview)
- [Anthropic Claude Code](https://www.anthropic.com/product/claude-code)
- [Google DeepMind Gemini 2.5 Pro](https://deepmind.google/technologies/gemini/pro)
- [Meta Llama 4 announcement](https://about.fb.com/news/2025/04/llama-4-multimodal-intelligence/)
- [McKinsey The state of AI in 2025](https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai/)
- [Model Context Protocol documentation](https://modelcontextprotocol.io/specification/draft)
- [Linux Foundation AAIF announcement](https://www.linuxfoundation.org/press/linux-foundation-announces-the-formation-of-the-agentic-ai-foundation)
- [OpenClaw docs](https://docs.openclaw.ai/index)
