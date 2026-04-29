---
marp: true
theme: default
paginate: true
style: |
  :root {
    --bg: #060b13;
    --bg2: #0d1320;
    --ink: #eef4ff;
    --muted: #9fb2cc;
    --cyan: #79d7ff;
    --green: #61e3a5;
    --amber: #f4c55d;
    --line: rgba(155, 180, 214, 0.18);
  }
  section {
    font-family: 'IBM Plex Sans', 'Avenir Next', 'Segoe UI', sans-serif;
    background:
      radial-gradient(circle at 82% 12%, rgba(121, 215, 255, 0.14), transparent 24%),
      radial-gradient(circle at 14% 88%, rgba(97, 227, 165, 0.12), transparent 22%),
      linear-gradient(180deg, var(--bg) 0%, var(--bg2) 100%);
    color: var(--ink);
    padding: 58px 72px;
  }
  section.cover {
    justify-content: center;
  }
  h1 {
    color: var(--ink);
    font-size: 2.78rem;
    line-height: 1.03;
    letter-spacing: -0.03em;
    margin: 0;
  }
  h2 {
    color: var(--cyan);
    font-size: 1.52rem;
    margin: 0 0 0.45em;
    letter-spacing: -0.02em;
  }
  h3 {
    color: var(--amber);
    font-size: 1rem;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    margin: 0 0 0.35em;
  }
  p, li {
    color: #dbe6f7;
    font-size: 1.02rem;
    line-height: 1.48;
  }
  ul, ol { margin: 0.35em 0 0.2em 1.1em; padding: 0; }
  li { margin: 0.12em 0; }
  strong { color: #ffffff; }
  a { color: var(--cyan); }
  code {
    background: rgba(121, 215, 255, 0.09);
    color: #effbff;
    padding: 0.08em 0.35em;
    border-radius: 5px;
    font-size: 0.92em;
  }
  pre {
    background: rgba(8, 14, 24, 0.76);
    border: 1px solid var(--line);
    border-radius: 14px;
    padding: 0.8em 0.95em;
    margin: 0.45em 0;
  }
  pre code {
    background: none;
    color: #eaf2ff;
    font-size: 0.9rem;
    line-height: 1.42;
  }
  blockquote {
    border-left: 4px solid var(--green);
    margin: 0.5em 0;
    padding: 0.55em 0.85em;
    background: rgba(97, 227, 165, 0.08);
    color: #edf6ff;
    border-radius: 0 10px 10px 0;
  }
  blockquote p { margin: 0; }
  table {
    border-collapse: collapse;
    width: 100%;
    margin: 0.35em 0 0.1em;
    font-size: 0.9rem;
  }
  th {
    background: rgba(121, 215, 255, 0.12);
    color: var(--cyan);
    text-align: left;
    padding: 8px 12px;
    border-bottom: 1px solid var(--line);
  }
  td {
    background: rgba(8, 14, 24, 0.48);
    color: #e2ebf8;
    padding: 8px 12px;
    border-bottom: 1px solid var(--line);
    vertical-align: top;
  }
  tr:nth-child(even) td { background: rgba(12, 20, 34, 0.76); }
  .eyebrow {
    color: var(--muted);
    letter-spacing: 0.18em;
    text-transform: uppercase;
    font-size: 0.74rem;
    margin-bottom: 0.7rem;
  }
  .deckline {
    color: var(--cyan);
    font-size: 1.12rem;
    margin-top: 0.35rem;
    max-width: 20em;
  }
  .note {
    color: var(--muted);
    font-size: 0.94rem;
    margin-top: 0.85rem;
    max-width: 30em;
  }
  .columns-3, .columns-2 {
    display: grid;
    gap: 20px;
    margin-top: 0.5rem;
  }
  .columns-3 { grid-template-columns: repeat(3, minmax(0, 1fr)); }
  .columns-2 { grid-template-columns: repeat(2, minmax(0, 1fr)); }
  .feature {
    padding-top: 12px;
    border-top: 1px solid var(--line);
  }
  .big {
    font-size: 1.33rem;
    line-height: 1.08;
    color: #ffffff;
    margin: 0 0 0.4em;
    letter-spacing: -0.03em;
  }
  .pipeline {
    margin-top: 0.25rem;
    color: #edf5ff;
    font-size: 1.12rem;
    line-height: 1.6;
    font-family: 'IBM Plex Mono', 'SFMono-Regular', Menlo, monospace;
  }
  .mini {
    color: var(--muted);
    font-size: 0.9rem;
    margin-top: 0.65rem;
  }
  .footerline {
    margin-top: 0.9rem;
    color: var(--muted);
    font-size: 0.92rem;
  }
---

<!-- _class: cover -->

<div class="eyebrow">State of AI / April 2026</div>

# The State of AI
## Technical overview

<div class="deckline">Architecture, models, retrieval, agents, MCP, and coding systems.</div>
<div class="note">This version keeps the details that matter to builders: what changed, how the stack fits together, and where the bottlenecks sit.</div>

---

## Timeline: from transformers to agent systems

<table>
  <thead>
    <tr><th style="width: 14%">Year</th><th>Milestone</th><th>Technical implication</th></tr>
  </thead>
  <tbody>
    <tr><td><strong>2017</strong></td><td>Transformer architecture</td><td>Attention becomes the backbone for foundation models.</td></tr>
    <tr><td><strong>2020</strong></td><td>GPT-3 scale-up</td><td>Few-shot behavior becomes visible at large scale.</td></tr>
    <tr><td><strong>2022</strong></td><td>ChatGPT and RLHF</td><td>Instruction following becomes a product surface.</td></tr>
    <tr><td><strong>2023</strong></td><td>Multimodal models mature</td><td>Text, image, and code move into one workflow.</td></tr>
    <tr><td><strong>2024</strong></td><td>Reasoning models mature</td><td>Test-time compute and deliberation become product features.</td></tr>
    <tr><td><strong>2025</strong></td><td>Coding agents ship</td><td>Models start reading repos, editing files, and running tools.</td></tr>
    <tr><td><strong>2026</strong></td><td>Agentic stacks standardize</td><td>Context, protocol, memory, and permissions become the real system.</td></tr>
  </tbody>
</table>

---

## Types of AI systems

<div class="columns-3">
  <div class="feature">
    <h3>Narrow</h3>
    <p>Single-task systems such as classifiers, detectors, and recommenders.</p>
  </div>
  <div class="feature">
    <h3>Generative</h3>
    <p>Models that produce text, image, audio, video, and code.</p>
  </div>
  <div class="feature">
    <h3>Multimodal</h3>
    <p>Systems that ingest and generate across text, image, audio, and video.</p>
  </div>
  <div class="feature">
    <h3>Reasoning</h3>
    <p>Inference-time deliberation that improves harder tasks.</p>
  </div>
  <div class="feature">
    <h3>Agentic</h3>
    <p>Multi-step systems that plan, act, observe, and revise.</p>
  </div>
  <div class="feature">
    <h3>Embodied</h3>
    <p>Models controlling physical systems, robots, or devices.</p>
  </div>
</div>

---

## How LLMs work in practice

- Base training is next-token prediction over large corpora.
- Instruction tuning and alignment make the model usable in product settings.
- Test-time compute changes the quality of the answer, not just the model weights.

<div class="columns-2">
  <div class="feature">
    <h3>Core metrics</h3>
    <p>Context window, latency, throughput, cost, and output length.</p>
  </div>
  <div class="feature">
    <h3>Evaluation axes</h3>
    <p>Reasoning, coding, knowledge, tool use, and visual understanding.</p>
  </div>
</div>

<blockquote>
  The hard question is no longer whether a model can answer. It is whether the system can reliably finish the job.
</blockquote>

---

## Retrieval augmented generation

<div class="pipeline">Question -> Embed -> Search -> Top chunks -> Prompt + context -> Answer</div>

<div class="columns-2">
  <div class="feature">
    <h3>What it solves</h3>
    <p>Stale training data, private knowledge, and context limits.</p>
  </div>
  <div class="feature">
    <h3>What it adds</h3>
    <p>Fresh grounding from documents, databases, and knowledge bases.</p>
  </div>
  <div class="feature">
    <h3>What matters</h3>
    <p>Chunking, embeddings, retrieval quality, and reranking.</p>
  </div>
  <div class="feature">
    <h3>Operational point</h3>
    <p>RAG is usually a system design problem before it is a model problem.</p>
  </div>
</div>

---

## Model landscape

<table>
  <thead>
    <tr><th>Vendor</th><th>Current family</th><th>Technical edge</th></tr>
  </thead>
  <tbody>
    <tr><td><strong>OpenAI</strong></td><td>GPT-5.5 / GPT-5.4 / GPT-5</td><td>Coding, tool use, and long-horizon work.</td></tr>
    <tr><td><strong>Anthropic</strong></td><td>Claude Opus 4.6 / Sonnet 4.6</td><td>Strong reasoning and code execution, 1M-token context beta.</td></tr>
    <tr><td><strong>Google DeepMind</strong></td><td>Gemini 2.5 Pro</td><td>1M-token context and strong multimodal reasoning.</td></tr>
    <tr><td><strong>Meta</strong></td><td>Llama 4 Scout / Maverick</td><td>Open weights, multimodality, and very long context.</td></tr>
  </tbody>
</table>

<div class="mini">The winning stack is model plus orchestration, not model alone.</div>

---

## Agent architecture

<div class="pipeline">Goal -> Planner -> Action -> Observation -> Memory -> Next action</div>

<div class="columns-3">
  <div class="feature">
    <h3>Memory</h3>
    <p>Context window, vector store, files, and state.</p>
  </div>
  <div class="feature">
    <h3>Tools</h3>
    <p>Search, shell, APIs, file systems, and browsers.</p>
  </div>
  <div class="feature">
    <h3>Planning</h3>
    <p>Task decomposition, self-correction, and retry logic.</p>
  </div>
</div>

<blockquote>
  Agents are software systems wrapped around a model, not the model itself.
</blockquote>

---

## MCP

MCP standardizes how an application exposes context to a model.

<div class="columns-3">
  <div class="feature">
    <h3>Tools</h3>
    <p>Callable actions with schemas.</p>
  </div>
  <div class="feature">
    <h3>Resources</h3>
    <p>Readable data from files, databases, or services.</p>
  </div>
  <div class="feature">
    <h3>Prompts</h3>
    <p>Reusable instruction templates and workflows.</p>
  </div>
</div>

- Client-server architecture keeps integrations portable.
- The spec supports local and remote transports.
- The Linux Foundation moved MCP into the Agentic AI Foundation in December 2025.

---

## Skills and coding agents

<table>
  <thead>
    <tr><th>System</th><th>What it packages</th><th>Why it matters</th></tr>
  </thead>
  <tbody>
    <tr><td><strong>Skills</strong></td><td>Reusable behavior</td><td>Workflow logic becomes a file, not a prompt fragment.</td></tr>
    <tr><td><strong>Claude Code</strong></td><td>Repo-scale coding agent</td><td>Reads code, edits files, runs tests, and commits changes.</td></tr>
    <tr><td><strong>Copilot Workspace</strong></td><td>Planning plus implementation</td><td>Moves from issue to patch through a guided workflow.</td></tr>
    <tr><td><strong>Cursor / Devin / OpenHands</strong></td><td>Different autonomy models</td><td>Show the spectrum from editor assist to delegated execution.</td></tr>
  </tbody>
</table>

---

## OpenClaw

<div class="columns-2">
  <div class="feature">
    <h3>Architecture</h3>
    <p>A self-hosted assistant with message-channel surfaces, a Gateway control plane, and model routing.</p>
  </div>
  <div class="feature">
    <h3>Skills</h3>
    <p>Packaged as directories containing `SKILL.md` instruction files.</p>
  </div>
  <div class="feature">
    <h3>Operational value</h3>
    <p>Local ownership, controlled routing, and reusable task behavior.</p>
  </div>
  <div class="feature">
    <h3>System lesson</h3>
    <p>The model is one component in a larger control plane.</p>
  </div>
</div>

<blockquote>
  OpenClaw is a useful example because it makes the control layer explicit.
</blockquote>

---

## Trends and open problems

<div class="columns-3">
  <div class="feature">
    <h3>Capability</h3>
    <p>Long-horizon task completion is still brittle.</p>
  </div>
  <div class="feature">
    <h3>Infrastructure</h3>
    <p>Permissioning, sandboxing, and auditability are becoming core product work.</p>
  </div>
  <div class="feature">
    <h3>Evaluation</h3>
    <p>Benchmarks matter less than task success in real workflows.</p>
  </div>
</div>

<div class="footerline">The bottleneck is shifting from model capability to orchestration quality.</div>

---

## Takeaways

<div class="columns-2">
  <div class="feature">
    <h3>1</h3>
    <p>Transformer architecture changed the model layer.</p>
  </div>
  <div class="feature">
    <h3>2</h3>
    <p>RAG, tools, and MCP changed the context layer.</p>
  </div>
  <div class="feature">
    <h3>3</h3>
    <p>Agents and skills changed the execution layer.</p>
  </div>
  <div class="feature">
    <h3>4</h3>
    <p>The next advantage is orchestration, not just raw model size.</p>
  </div>
</div>

---

<!-- _class: cover -->

<div class="eyebrow">State of AI / April 2026</div>
<h1>Thank you</h1>
<div class="note">See <code>ai-state-research.md</code> for source links and claim notes.</div>
