---
marp: true
theme: default
paginate: true
style: |
  :root {
    --bg: #08121c;
    --bg2: #101b2b;
    --ink: #f4f8ff;
    --muted: #a9b8cf;
    --cyan: #67e8f9;
    --amber: #fbbf24;
    --coral: #fb7185;
    --line: rgba(170, 190, 220, 0.18);
  }
  section {
    font-family: 'Avenir Next', 'Segoe UI', sans-serif;
    background:
      radial-gradient(circle at 12% 12%, rgba(251, 191, 36, 0.14), transparent 20%),
      radial-gradient(circle at 84% 14%, rgba(103, 232, 249, 0.14), transparent 22%),
      linear-gradient(180deg, var(--bg) 0%, var(--bg2) 100%);
    color: var(--ink);
    padding: 58px 72px;
  }
  section.cover {
    justify-content: center;
  }
  h1 {
    color: var(--ink);
    font-size: 2.9rem;
    line-height: 1.02;
    margin: 0;
    letter-spacing: -0.03em;
  }
  h2 {
    color: var(--cyan);
    font-size: 1.6rem;
    margin: 0 0 0.45em;
    letter-spacing: -0.02em;
  }
  h3 {
    color: var(--amber);
    font-size: 1rem;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    margin: 0 0 0.35em;
  }
  p, li {
    color: #dfe7f5;
    font-size: 1.08rem;
    line-height: 1.5;
  }
  ul, ol {
    margin: 0.35em 0 0.2em 1.1em;
    padding: 0;
  }
  li { margin: 0.12em 0; }
  strong { color: #ffffff; }
  a { color: var(--cyan); }
  code {
    background: rgba(103, 232, 249, 0.1);
    color: #e9feff;
    padding: 0.08em 0.35em;
    border-radius: 5px;
    font-size: 0.92em;
  }
  pre {
    background: rgba(8, 18, 28, 0.72);
    border: 1px solid var(--line);
    border-radius: 14px;
    padding: 0.75em 0.9em;
  }
  pre code {
    background: none;
    color: #eef5ff;
    font-size: 0.92rem;
  }
  blockquote {
    border-left: 4px solid var(--coral);
    margin: 0.5em 0;
    padding: 0.55em 0.85em;
    background: rgba(251, 113, 133, 0.08);
    color: #eef4ff;
    border-radius: 0 10px 10px 0;
  }
  blockquote p { margin: 0; }
  table {
    border-collapse: collapse;
    width: 100%;
    margin: 0.35em 0 0.1em;
    font-size: 0.95rem;
  }
  th {
    background: rgba(103, 232, 249, 0.12);
    color: var(--cyan);
    text-align: left;
    padding: 8px 12px;
    border-bottom: 1px solid var(--line);
  }
  td {
    background: rgba(8, 18, 28, 0.44);
    color: #e2ebf8;
    padding: 8px 12px;
    border-bottom: 1px solid var(--line);
  }
  tr:nth-child(even) td { background: rgba(12, 24, 38, 0.72); }
  .eyebrow {
    color: var(--muted);
    letter-spacing: 0.18em;
    text-transform: uppercase;
    font-size: 0.74rem;
    margin-bottom: 0.7rem;
  }
  .deckline {
    color: var(--cyan);
    font-size: 1.14rem;
    max-width: 18em;
    margin-top: 0.35rem;
  }
  .note {
    color: var(--muted);
    font-size: 0.98rem;
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
    font-size: 1.4rem;
    line-height: 1.05;
    color: #ffffff;
    margin: 0 0 0.4em;
    letter-spacing: -0.03em;
  }
  .pipeline {
    margin-top: 0.25rem;
    color: #eef5ff;
    font-size: 1.18rem;
    line-height: 1.7;
  }
  .takeaway {
    border-top: 1px solid var(--line);
    padding-top: 12px;
  }
  .takeaway strong {
    color: var(--amber);
    display: block;
    margin-bottom: 0.35rem;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    font-size: 0.8rem;
  }
  .takeaway p {
    margin: 0;
    font-size: 1.18rem;
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
## A plain-English snapshot

<div class="deckline">AI is moving from chat as a feature to agent systems that actually do work.</div>
<div class="note">This version is for a non-technical audience: fewer terms, fewer acronyms, and a sharper focus on what changed.</div>

---

## The short answer

<div class="columns-3">
  <div class="feature">
    <div class="big">AI is now normal.</div>
    <p>Most organizations already use it in at least one business function.</p>
  </div>
  <div class="feature">
    <div class="big">The next step is agency.</div>
    <p>Instead of only answering questions, systems can now take actions.</p>
  </div>
  <div class="feature">
    <div class="big">Value comes from redesigning work.</div>
    <p>The biggest gains happen when teams change the process, not just the prompt.</p>
  </div>
</div>

---

## How the story changed

<table>
  <thead>
    <tr><th style="width: 18%">Then</th><th>Now</th></tr>
  </thead>
  <tbody>
    <tr><td><strong>Ask a question</strong></td><td>Give a goal and let the system work through steps.</td></tr>
    <tr><td><strong>One answer</strong></td><td>Search, draft, revise, and complete the task.</td></tr>
    <tr><td><strong>Manual knowledge work</strong></td><td>AI helps with writing, coding, research, and operations.</td></tr>
    <tr><td><strong>One tool at a time</strong></td><td>Models connect to files, apps, and services.</td></tr>
  </tbody>
</table>

---

## What AI can create now

<div class="columns-2">
  <div class="feature">
    <h3>Text and code</h3>
    <p>Emails, summaries, reports, and software.</p>
  </div>
  <div class="feature">
    <h3>Images and video</h3>
    <p>Visual drafts, product shots, and short clips.</p>
  </div>
  <div class="feature">
    <h3>Audio</h3>
    <p>Voice, narration, and music generation.</p>
  </div>
  <div class="feature">
    <h3>Analysis</h3>
    <p>Research, comparison, and document review.</p>
  </div>
</div>

<blockquote>
  AI is no longer just a writing assistant. It is becoming a general-purpose work assistant.
</blockquote>

---

## What an AI agent is

<div class="pipeline">Goal → Plan → Act → Check → Adjust → Finish</div>

- A chatbot waits for the next question.
- An agent keeps going until the goal is done.
- The best agents can search, read, write, and update other systems.

<div class="note">That is why "agent" is the important word in 2026.</div>

---

## The pieces that make agents useful

<div class="columns-3">
  <div class="feature">
    <h3>Memory</h3>
    <p>Remember the task and what matters.</p>
  </div>
  <div class="feature">
    <h3>Tools</h3>
    <p>Reach into apps, files, and services.</p>
  </div>
  <div class="feature">
    <h3>Skills</h3>
    <p>Reuse proven workflows for repeat work.</p>
  </div>
</div>

---

## Why MCP matters

- It gives AI a standard way to connect to tools and data.
- It reduces custom one-off integrations.
- It makes models more portable across products.

<blockquote>
  Think of MCP as the shared connector layer for AI.
</blockquote>

---

## The new work pattern

<div class="columns-2">
  <div class="feature">
    <h3>Old pattern</h3>
    <p>People did the task. Software recorded the result.</p>
  </div>
  <div class="feature">
    <h3>New pattern</h3>
    <p>People set direction. AI helps execute the work.</p>
  </div>
</div>

- This is already happening in coding, support, research, and operations.
- The highest value comes from work that has clear steps and repeatable decisions.

---

## The one thing to remember

<div class="takeaway">
  <strong>Takeaway</strong>
  <p>AI is becoming an assistant you direct, not just a tool you use.</p>
</div>

<div class="footerline">The best teams will not ask, "What can AI answer?" They will ask, "What work can AI finish?"</div>

---

<!-- _class: cover -->

<div class="eyebrow">State of AI / April 2026</div>
<h1>Thank you</h1>
<div class="note">Research notes are in <code>ai-state-research.md</code>.</div>
