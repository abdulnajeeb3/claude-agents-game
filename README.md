# Claude Agents Game

A pixel-art mission control for Claude Code agents — watch every agent work live, hand them tasks, and grow them into a small agent-run company.

> Work in progress. Built in public, one phase at a time.

## How it works

```
Claude Code sessions ──hooks (JSON)──▶ Event server ──▶ SQLite
   ▲                                   │
   │ spawns headless `claude -p`        ▼ WebSocket
Orchestrator ◀── task board ──── Dashboard / pixel office (browser)
```

Claude Code [hooks](https://docs.claude.com/en/docs/claude-code/hooks) stream every tool call, permission prompt, and session event to a local server. The dashboard renders each agent as a character whose animation reflects what it's doing.

## Roadmap

- [ ] **1. Live tracker** — hooks → event server → SQLite → live web dashboard of all sessions
- [ ] **2. Office** — pixel-art view (Phaser); agent states map to animations
- [ ] **3. Dispatch** — task board that spawns headless `claude -p` workers with roles, each in its own git worktree
- [ ] **4. Company** — roles, goals, scheduled heartbeats, usage budgets, human approval inbox
- [ ] **5. Revenue** — one real business loop run by the agents

## Stack

TypeScript · Node · Hono · SQLite · Vite + React · Phaser

## Privacy

Everything runs locally. Agent event data (`data/`, `*.db`) is git-ignored and never leaves your machine.
