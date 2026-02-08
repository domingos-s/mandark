![Mandark](mandark.jpg)

# Mandark

Mandark is a **Codex-driven research operator** designed to run inside VS Code.  
It replicates the core behavior of the Dexter repo—agent loop, tool calls, scratchpad logging, and replayability—while remaining **API-key free**, **deterministic**, and **audit-friendly**.

Think of Mandark as a retro-styled rival brain: precise, obsessive, and built for repeatable research.

---

## Core Principles

- **Chat-first UX**  
  You interact with Mandark through Codex chat commands.

- **File-backed execution**  
  Every run produces durable artifacts you can inspect, diff, and replay.

- **No API keys**  
  Mandark relies only on public, credible data sources and Codex’s built-in LLM capability.

- **Verbatim input capture**  
  The user’s question is written **verbatim, byte-for-byte** as the first content in the session file.  
  Whitespace, punctuation, and newlines are preserved exactly.

- **Tool summaries only**  
  No hidden reasoning is shown.  
  Full trace lives in the scratchpad JSONL.

---

## Folder Structure

Mandark is self-contained inside its own folder.

```
Mandark/
├─ MANDARK_PLAYBOOK.md
├─ MANDARK_RUNBOOK.md
├─ MANDARK_SESSION_TEMPLATE.md
├─ MANDARK_SCRATCHPAD_SCHEMA.md
├─ README.md
├─ sessions/
│  └─ YYYY-MM-DD/
│     └─ <run_id>_<slug>.md
└─ .mandark/
   ├─ scratchpad/
   │  └─ <run_id>.jsonl
   └─ raw/               # optional
```

All paths are **relative to the Mandark folder root**.

---

## Supported Commands

Use these directly in Codex chat:

- `Mandark: run <question>`
- `Mandark: show <run_id>`
- `Mandark: replay <run_id>`
- `Mandark: help`

---

## Getting Started

1. Open VS Code at the parent `Codex/` folder.
2. Ensure Mandark lives at `Codex/Mandark/`.
3. Enter Codex Agent Mode.
4. Paste the Mandark Agent instruction.
5. Run:

```
Mandark: run hello
```

If that works, Mandark is alive.
