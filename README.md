# agents-standard

[![CI](https://img.shields.io/github/actions/workflow/status/fuzzywigg/agents-standard/ci.yml?branch=alpha&label=CI)](https://github.com/fuzzywigg/agents-standard/actions/workflows/ci.yml)
[![AGENTS.md](https://img.shields.io/badge/AGENTS.md-v3.2.0-blue)](AGENTS.md)

Public markdown dump. Default branch is `alpha`. Not a product, runtime, or app.

The only real artifact is [`AGENTS.md`](AGENTS.md) v3.2.0 — FUZZYWIGG-AI agent operating protocol. Paste it into a system prompt if you want that protocol.

Also on the tree: `CLAUDE.md`, hydration notes, a `postmortem.md` template, a scratchpad stub, and a Copilot agent file.

Thin CI: [`.github/workflows/ci.yml`](.github/workflows/ci.yml) (markdown lint + link check). No LICENSE yet.

## Cloud agents

Docs-only bootstrap lives in [`.cursor/environment.json`](.cursor/environment.json) (`install` verifies key files; no `start` services).

Sibling archive: [g0p-agents](https://github.com/fuzzywigg/g0p-agents) (older v2.2 prompts + CI templates).
