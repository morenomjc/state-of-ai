---
marp: true
theme: default
paginate: true
style: |
  :root {
    --bg: #07111f;
    --bg2: #0d1628;
    --ink: #edf4ff;
    --muted: #9fb0cc;
    --soft: #c9d4ea;
    --cyan: #7dd3fc;
    --violet: #a78bfa;
    --gold: #fbbf24;
    --green: #34d399;
    --line: rgba(160, 180, 214, 0.16);
  }
  section {
    font-family: 'Avenir Next', 'Segoe UI', sans-serif;
    background:
      radial-gradient(circle at 85% 10%, rgba(167, 139, 250, 0.18), transparent 25%),
      radial-gradient(circle at 15% 90%, rgba(125, 211, 252, 0.14), transparent 24%),
      linear-gradient(180deg, var(--bg) 0%, var(--bg2) 100%);
    color: var(--ink);
    padding: 60px 72px;
  }
  section.cover {
    justify-content: center;
    padding-right: 96px;
  }
  h1 {
    color: var(--ink);
    font-size: 2.75rem;
    line-height: 1.03;
    letter-spacing: -0.03em;
    margin: 0;
  }
  h2 {
    color: var(--cyan);
    font-size: 1.55rem;
    margin: 0 0 0.5em;
    letter-spacing: -0.02em;
  }
  h3 {
    color: var(--gold);
    font-size: 1.02rem;
    margin: 0 0 0.35em;
    letter-spacing: 0.02em;
    text-transform: uppercase;
  }
  p, li {
    color: var(--soft);
    font-size: 1.04rem;
    line-height: 1.48;
  }
  ul, ol {
    margin: 0.35em 0 0.2em 1.1em;
    padding: 0;
  }
  li { margin: 0.12em 0; }
  strong { color: #ffffff; }
  a { color: var(--cyan); }
  code {
    background: rgba(125, 211, 252, 0.1);
    color: #dff7ff;
    padding: 0.08em 0.35em;
    border-radius: 5px;
    font-size: 0.92em;
  }
  pre {
    background: rgba(10, 18, 31, 0.72);
    border: 1px solid var(--line);
    border-radius: 14px;
    padding: 0.75em 0.9em;
    margin: 0.45em 0;
  }
  pre code {
    background: none;
    color: #dce6f7;
    font-size: 0.88rem;
    line-height: 1.42;
  }
  blockquote {
    border-left: 4px solid var(--violet);
    margin: 0.55em 0;
    padding: 0.55em 0.85em;
    color: #d7def0;
    background: rgba(167, 139, 250, 0.08);
    border-radius: 0 10px 10px 0;
  }
  blockquote p { margin: 0; }
  table {
    border-collapse: collapse;
    width: 100%;
    margin: 0.35em 0 0.1em;
    font-size: 0.82rem;
  }
  th {
    background: rgba(125, 211, 252, 0.12);
    color: var(--cyan);
    text-align: left;
    padding: 7px 10px;
    border-bottom: 1px solid var(--line);
  }
  td {
    background: rgba(10, 18, 31, 0.48);
    color: #e2eaf8;
    padding: 7px 10px;
    border-bottom: 1px solid var(--line);
    vertical-align: top;
  }
  tr:nth-child(even) td {
    background: rgba(11, 21, 38, 0.75);
  }
  .eyebrow {
    color: var(--muted);
    letter-spacing: 0.18em;
    text-transform: uppercase;
    font-size: 0.74rem;
    margin-bottom: 0.75rem;
  }
  .deckline {
    color: var(--cyan);
    font-size: 1.1rem;
    margin-top: 0.4rem;
    max-width: 16em;
  }
  .cover-note {
    color: var(--muted);
    font-size: 1.02rem;
    margin-top: 1rem;
    max-width: 28em;
  }
  .columns-3, .columns-2 {
    display: grid;
    gap: 22px;
    margin-top: 0.5rem;
  }
  .columns-3 { grid-template-columns: repeat(3, minmax(0, 1fr)); }
  .columns-2 { grid-template-columns: repeat(2, minmax(0, 1fr)); }
  .feature {
    padding-top: 12px;
    border-top: 1px solid var(--line);
  }
  .feature p {
    margin: 0;
  }
  .feature .big {
    font-size: 1.35rem;
    line-height: 1.05;
    margin: 0 0 0.45em;
    color: #ffffff;
    letter-spacing: -0.03em;
  }
  .feature .accent {
    color: var(--cyan);
    font-weight: 700;
  }
  .pipeline {
    margin-top: 0.2rem;
    color: #dfe8f8;
    font-size: 1.18rem;
    line-height: 1.7;
    letter-spacing: -0.01em;
  }
  .timeline {
    font-size: 1rem;
    line-height: 1.5;
  }
  .timeline strong {
    color: var(--gold);
  }
  .takeaways {
    display: grid;
    grid-template-columns: repeat(3, minmax(0, 1fr));
    gap: 24px;
    margin-top: 1rem;
  }
  .takeaway {
    border-top: 1px solid var(--line);
    padding-top: 12px;
  }
  .takeaway .num {
    color: var(--cyan);
    font-size: 0.85rem;
    letter-spacing: 0.18em;
    text-transform: uppercase;
    margin-bottom: 0.5rem;
  }
  .takeaway p {
    margin: 0;
    color: #eef4ff;
    font-size: 1.12rem;
    line-height: 1.45;
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
## Models, agents, and the control layer

<div class="deckline">The shift is from prompting models to operating systems for work.</div>
<div class="cover-note">A concise view of what changed, what matters now, and where the leverage is moving.</div>

---

## The thesis

<div class="columns-3">
  <div class="feature">
    <div class="big">1. Models are good enough for real work.</div>
    <p>The frontier is still moving, but quality is no longer the main bottleneck.</p>
  </div>
  <div class="feature">
    <div class="big">2. Context decides usefulness.</div>
    <p>The winning system is the model plus retrieval, tools, permissions, and memory.</p>
  </div>
  <div class="feature">
    <div class="big">3. The unit of value is the completed task.</div>
    <p>Agents matter because they close loops, not because they answer questions.</p>
  </div>
</div>

<div class="footerline">Prompt → Context → Tools → Task complete</div>

---

## From lab breakthrough to workflow layer

<table class="timeline">
  <thead>
    <tr><th style="width: 14%">Year</th><th>Shift</th><th>Why it matters</th></tr>
  </thead>
  <tbody>
    <tr><td><strong>1950s-2016</strong></td><td>Symbolic AI, then deep learning</td><td>Research shifts from rule systems to data-driven models.</td></tr>
    <tr><td><strong>2017</strong></td><td>Transformers arrive</td><td>The architecture behind modern foundation models appears.</td></tr>
    <tr><td><strong>2022</strong></td><td>ChatGPT goes mainstream</td><td>Natural-language interfaces become a consumer product.</td></tr>
    <tr><td><strong>2024-25</strong></td><td>Reasoning and coding agents</td><td>Models start planning, calling tools, and completing tasks.</td></tr>
    <tr><td><strong>2026</strong></td><td>Agents become the product surface</td><td>Control layers, standards, and orchestration matter more than prompts.</td></tr>
  </tbody>
</table>

---

## Model competition is now about systems

<div class="columns-2">
  <div class="feature">
    <h3>OpenAI</h3>
    <p><strong>GPT-5.5 / GPT-5.4 / GPT-5</strong><br>Latest releases focus on coding, research, and tool-heavy work.</p>
  </div>
  <div class="feature">
    <h3>Anthropic</h3>
    <p><strong>Claude Opus 4.6 / Sonnet 4.6</strong><br>Strong reasoning and coding, with 1M-token context in beta.</p>
  </div>
  <div class="feature">
    <h3>Google DeepMind</h3>
    <p><strong>Gemini 2.5 Pro</strong><br>1M-token context and strong coding / multimodal performance.</p>
  </div>
  <div class="feature">
    <h3>Meta</h3>
    <p><strong>Llama 4 Scout / Maverick</strong><br>Open weights, native multimodality, and very long context.</p>
  </div>
</div>

<div class="footerline">The differentiator is not just model quality. It is fit for the task.</div>

---

## RAG gives models fresh context

<div class="pipeline">
Question → Embed → Search → Top chunks → Prompt + context → Answer
</div>

- <strong>Chunking</strong>: split source material into retrievable pieces.
- <strong>Embeddings</strong>: turn meaning into vectors.
- <strong>Vector search</strong>: find relevant context at query time.
- <strong>Reranking</strong>: improve precision before the model answers.

<blockquote>
  The point of RAG is not to make models smarter. It is to make them better informed.
</blockquote>

---

## Agents are loops, not prompts

<div class="pipeline">
Goal → Plan → Act → Observe → Revise → Act → Done
</div>

<div class="columns-2">
  <div class="feature">
    <h3>Memory</h3>
    <p>Short-term context plus long-term state.</p>
  </div>
  <div class="feature">
    <h3>Tools</h3>
    <p>Search, code execution, file I/O, APIs, browsers.</p>
  </div>
  <div class="feature">
    <h3>Planning</h3>
    <p>Break the goal into steps and recover from mistakes.</p>
  </div>
  <div class="feature">
    <h3>Skills</h3>
    <p>Reusable playbooks for repeatable work.</p>
  </div>
</div>

---

## MCP and skills are the connector layer

<div class="columns-3">
  <div class="feature">
    <h3>Tools</h3>
    <p>Actions the model can take.</p>
  </div>
  <div class="feature">
    <h3>Resources</h3>
    <p>Data the model can read.</p>
  </div>
  <div class="feature">
    <h3>Prompts</h3>
    <p>Reusable workflows and templates.</p>
  </div>
</div>

<blockquote>
  MCP standardizes how applications provide context to models, so agents do not need one-off integrations for every tool.
</blockquote>

- The Model Context Protocol uses a client-server architecture. [Docs](https://modelcontextprotocol.io/specification/draft)
- The Linux Foundation moved MCP into the Agentic AI Foundation in December 2025. [LF](https://www.linuxfoundation.org/press/linux-foundation-announces-the-formation-of-the-agentic-ai-foundation)
- OpenClaw-style skills are directory-based instructions in `SKILL.md` files. [OpenClaw](https://docs.openclaw.ai/tools/skills)

---

## Coding agents have crossed into production

<table>
  <thead>
    <tr><th>Agent</th><th>Best at</th><th>What changed</th></tr>
  </thead>
  <tbody>
    <tr><td><strong>Claude Code</strong></td><td>Repo-scale edits and tool use</td><td>Reads codebases, makes changes, runs tests, and commits working code.</td></tr>
    <tr><td><strong>Copilot Workspace</strong></td><td>PR-centered workflows</td><td>Turns plans into edits and tests inside developer workflows.</td></tr>
    <tr><td><strong>Cursor</strong></td><td>Editor-native coding</td><td>Brings agentic help into the IDE itself.</td></tr>
    <tr><td><strong>Devin</strong></td><td>Long-horizon tasks</td><td>Shows what a more autonomous coding system looks like.</td></tr>
  </tbody>
</table>

<div class="footerline">The shift is from autocomplete to delegated execution.</div>

---

## Local-first agents move the control plane to your machine

<div class="columns-2">
  <div class="feature">
    <h3>OpenClaw pattern</h3>
    <p>A self-hosted assistant that runs on your own devices and connects through the chat surfaces you already use.</p>
  </div>
  <div class="feature">
    <h3>Why it matters</h3>
    <p>Ownership, privacy, and workspace control become product features instead of afterthoughts.</p>
  </div>
  <div class="feature">
    <h3>Skills</h3>
    <p>Behavior is packaged as reusable instruction folders, not hard-coded logic.</p>
  </div>
  <div class="feature">
    <h3>Model-agnostic</h3>
    <p>The control plane can route different models to different tasks.</p>
  </div>
</div>

<div class="footerline">The important architectural idea is separation: model, memory, tools, and user-facing channels are not the same thing.</div>

---

## What matters now

<div class="takeaways">
  <div class="takeaway">
    <div class="num">01</div>
    <p>AI adoption is broad, but most organizations still need workflow redesign to capture value.</p>
  </div>
  <div class="takeaway">
    <div class="num">02</div>
    <p>Model choice matters, but context, tools, and orchestration increasingly decide outcome quality.</p>
  </div>
  <div class="takeaway">
    <div class="num">03</div>
    <p>The winning systems are turning from chat interfaces into action systems.</p>
  </div>
</div>

<div class="footerline">The new skill is not prompting. It is directing systems.</div>

---

<!-- _class: cover -->

<div class="eyebrow">State of AI / April 2026</div>
<h1>Thank you</h1>
<div class="deckline">Sources and research notes live in the companion memo.</div>
