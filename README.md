# AI Agent System Prompt — Senior‑Engineer Behavioral Framework

A ready‑to‑adopt system prompt that turns any capable LLM coding agent into a disciplined, honest senior engineer. It encodes adversarial thinking, strict approval boundaries, honest diagnostics, code‑quality rules, and a directive command language — so you get a strategic mirror, not a cheerleader.

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Repo Size](https://img.shields.io/github/repo-size/dimassaa/ai-agent-system-prompt)

---

## Table of Contents

- [Introduction](#introduction)
- [Why This Prompt Exists](#why-this-prompt-exists)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [Key Features](#key-features)
- [Directive Commands](#directive-commands)
- [Limitations](#limitations)
- [Recommendations](#recommendations)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgements](#acknowledgements)

---

## Introduction

This repository publishes the **`AGENTS.md`** file — a complete behavioral contract for an AI coding agent. Where most agent prompts optimize for obedience, this one optimizes for **truthfulness and discipline**.

It installs a set of immutable rules into the agent's working context:

- **Advisor stance** — the agent is a strategic mirror that challenges weak reasoning, never validates ego, and never invents problems to seem useful.
- **Strict approval boundary** — no functional changes without explicit consent, while still permitting clearly documented non‑functional fixes.
- **Honest diagnostics** — a rigorous discipline for reporting "no defects" when none exist, classifying speculative risks correctly, and never concealing findings.
- **Quality‑first code** — obvious over clever, maintainable over elegant, comments that explain *why*, and dead code deleted.
- **A directive command language** — `PLAN APPROVED`, `PONYTAIL REVIEW`, `DOCS UPDATE`, `CODE REVIEW`, `GRILL`, `SUMMARIZE`, and `HALT` unlock structured workflows on demand.

It is optimized for agents that have access to **codebase‑memory‑MCP** (a knowledge‑graph tool for code discovery), but the agent‑behavior sections are tool‑agnostic and carry over to any coding agent.

---

## Why This Prompt Exists

Default agent behavior has a known failure mode: it is agreeable. It flatters, complies blindly, and hides uncertainty. Over months of use this silently degrades code quality, buries real risks, and lets junior‑level mistakes pass unreviewed.

This prompt is a deliberate corrective. It treats the agent as a **senior engineer with a spine**:

- Between 0% and 100% honesty, it selects 100% — even when that is uncomfortable.
- Between "just do it" and "ask first," it selects **ask first** whenever behavior would change.
- Between bloat and minimalism, it selects minimal and forces justification for every abstraction.

The outcome is a partner that challenges the plan before it is approved, executes precisely once approved, and halts loudly when it hits a real blocker.

---

## Project Structure

```
ai-agent-system-prompt/
├── AGENTS.md                     # The system prompt / behavioral contract (the artifact)
├── README.md                     # You are here
└── LICENSE                       # MIT license
```

- **`AGENTS.md`** — the single file to drop into your project (or reference as context) to install the behavioral framework.

---

## Getting Started

### Prerequisites

- An AI coding agent that supports a project‑level instruction file (e.g., an `AGENTS.md`, `CLAUDE.md`, or custom instructions file), and/or
- An agent with access to `codebase-memory-mcp` for the optional graph‑based code discovery features (Section 4 of the prompt).

### Installation

1. **Copy the prompt into your project:**

   ```bash
   cp AGENTS.md <your-project>/AGENTS.md
   ```

2. **Or reference it as agent context** — in whatever mechanism your agent uses to load persistent instructions (custom instructions, a knowledge file, or a rules file).

3. **Optional (graph‑based code discovery):** ensure your agent has `codebase-memory-mcp` configured and indexing your repository, then the priority‑order and evidence‑tier rules in Section 4 take effect automatically.

### Usage

Once loaded, the agent operates under the full contract. There is no "run" step — the instructions govern every interaction. The most visible feature is the directive command language: issue one of the commands below in your normal chat and the agent follows the corresponding workflow.

---

## Key Features

| Feature | What it does |
|---------|--------------|
| Advisor stance | Challenges weak reasoning, exposes blind spots, refuses to validate ego. |
| Honesty discipline | Reports "Nothing to report" when clean; never fabricates issues. |
| Approval boundary | No functional change without consent; documents every non‑functional edit. |
| Uncertainty protocol | Surfaces alternative interpretations, proposes a default, and waits for confirmation — no silent assumptions. |
| Code‑quality rules | Obvious code, documented reasoning, fail‑fast validation, zero dead code. |
| Knowledge‑graph integration | Priority‑ordered MCP tools with tiered evidence standards for code discovery. |
| Directive language | Seven structured commands for plan‑based and review‑based workflows. |

---

## Directive Commands

These exact phrases trigger structured agent workflows — no deviation:

| Command | Workflow triggered |
|---------|--------------------|
| `PLAN APPROVED` | Acknowledge plan, execute only the first step, wait for confirmation. |
| `PONYTAIL REVIEW` | Audit for over‑engineering; report only, no refactor. |
| `DOCS UPDATE` | Scan docs against reality, flag staleness, update, and commit. |
| `CODE REVIEW` | Run the requesting‑code‑review skill against the current work. |
| `GRILL` / `GRILL WITH DOCS` | Additively interrogate the plan; optionally produce an ADR + glossary. |
| `SUMMARIZE` | Tight bullet‑point stage summary. |
| `HALT` | Stop all execution immediately, await explanation. |

---

## Limitations

Be honest about what this prompt does **not** do:

- It does not replace human oversight — it *increases* the agent's assertiveness, so it will push back and sometimes pause work that a human manager is not expecting to be paused.
- The full code‑discovery workflow requires `codebase-memory-mcp`; without it, Section 4 is inert and the agent falls back to grep/glob.
- Its strictness (ask‑before‑acting, stage‑by‑stage execution) is slower for trivial, single‑step tasks where a more permissive agent would just act.
- It is a behavioral contract, not a task executor — results depend entirely on the underlying model's reasoning capability.

---

## Recommendations

- Start on a **non‑critical project** you already know well — the first few interactions show a noticeably more assertive agent, and it helps to calibrate expectations before it runs on anything urgent.
- Use the **directive commands** as the primary interface for multi‑step work; they impose the discipline the prompt describes.
- If your agent doesn't support `codebase-memory-mcp`, either install it or expect the code‑discovery sections to be skipped.
- Adapt the "Directive Commands" list to your own workflow markers — they are examples of the pattern, not a hard API.

---

## Contributing

Contributions are welcome. Please:

1. Open an issue describing the behavior change or addition you want before submitting a PR.
2. Keep the prompt's voice and structure — every rule must stay a clear, self‑contained instruction that answers *why*.
3. Add a short note in your PR explaining the rationale, alternatives considered, and any trade‑offs.

See the issue tracker for open work. Pull requests are reviewed against the philosophy in [Why This Prompt Exists](#why-this-prompt-exists).

---

## License

Distributed under the [MIT License](LICENSE). See `LICENSE` for details.

---

## Acknowledgements

- Inspired by the recurring failure mode of agreeable coding agents — and by the programming style guides that insist code be written for the human reading it at 3 AM.
