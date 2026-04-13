# CLAUDE.md — agents-standard

> **Repo-specific agent instructions for the `fuzzywigg/agents-standard` repository.**
> This file augments the root `AGENTS.md` with context specific to this repo's purpose and workflows.

---

## Repository Purpose

`agents-standard` is the **public-facing canonical reference** for the FUZZYWIGG-AI Ecosystem's agent operating protocols. Its primary artifact is `AGENTS.md` (v3.2.0) — the persistent cognitive context injected into all agents at session start.

This repo is a **documentation/standards repo**, not an executable codebase. There is no build step, no runtime, and no test suite in the traditional sense. Validation is via Markdown linting and structural audits.

---

## Agent Routing for This Repo

| Surface | Tasks |
|---------|-------|
| `copilot` | Markdown formatting, governance file creation, CI workflow setup, README/CHANGELOG updates |
| `claude-cowork` | Strategic decisions, cross-repo alignment, Notion sync, architecture questions |
| `browser-claude` | GitHub Settings UI (branch protection, repo visibility, CODEOWNERS enforcement) |
| `human` | LICENSE disputes, repo visibility changes, financial/billing decisions |

---

## Working in This Repo

### Files and Their Owners

| File | Owner | Edit Policy |
|------|-------|-------------|
| `AGENTS.md` | Andrew Pappas (smtp.eth) | Agent-editable content; structural/version changes require Andrew approval |
| `README.md` | Agent-editable | Minor updates OK; messaging changes require Andrew review |
| `CLAUDE.md` | Agent-editable | Freely editable by agents; reflect actual repo state |
| `docs/` | Agent-editable | Agents may create and update docs freely |
| `.github/workflows/` | Agent-editable | CI changes require passing validation before merge |
| `AGENTS.md` version bump | Human approval | Increment `agent_version` and `last_updated` only with Andrew sign-off |

### Branch Strategy

```
alpha (default — treat as main for this repo)
  └── copilot/[task-name]   ← All agent work branches
```

- **Never commit directly to `alpha`** — always work on a branch and open a PR
- Branch naming: `copilot/[task-name]`, `fix/[issue-number]`, `docs/[scope]`

### Validation Commands

```bash
# Markdown lint (install if needed)
npx markdownlint-cli "**/*.md" --ignore node_modules

# Check for broken internal links
npx markdown-link-check README.md AGENTS.md CLAUDE.md

# Spell check (optional)
npx cspell "**/*.md"
```

### No Build, No Tests

This repo has no `package.json`, no Python environment, no compiled artifacts. If you find yourself writing code that needs to be executed, you are likely working in the wrong repo — escalate to `claude-cowork` to determine the correct target repo.

---

## AGENTS.md Versioning Protocol

When updating `AGENTS.md`:

1. Increment `agent_version` in the YAML frontmatter (semver: `MAJOR.MINOR.PATCH`)
2. Update `last_updated` date
3. Add a row to the **Version History** table (Part 18.2)
4. Note the approver (agent name or "Human")
5. Open a PR — do **not** merge directly to `alpha`

**Version bump authority:**
- `PATCH` (typos, clarifications) → Agent-editable, self-merge OK if CI passes
- `MINOR` (new sections, new patterns) → Requires Andrew review before merge
- `MAJOR` (structural overhaul, constraint changes) → Requires Andrew approval + explicit sign-off comment

---

## Known Gaps (as of 2026-04-13)

These are tracked in `docs/hydration-issues.md` and should be converted to GitHub Issues:

- No LICENSE file
- No CI/CD workflows
- No issue/PR templates
- No CONTRIBUTING.md or SECURITY.md
- `README.md` has `[PROJECT_NAME]` placeholder
- `agentic_flows/scratchpad.txt` referenced in AGENTS.md frontmatter but not present
- `postmortem.md` referenced in AGENTS.md frontmatter but not present

See `docs/hydration-issues.md` for the full prioritized issue backlog.

---

## Cross-System Links

> These are public-facing governance links for the FUZZYWIGG-AI Ecosystem. They are intentionally listed here for agent discovery. If you encounter an access restriction, contact Andrew Pappas (smtp.eth) for access.

| System | Link | What lives there |
|--------|------|-----------------|
| Notion Master Index | https://www.notion.so/337071e361d28189b501ce2a1983a239 | Governance index |
| Notion Tier 0 (Agent Interface) | https://www.notion.so/33f071e361d2814fb6d0db6d54a1a651 | Agent operating rules |
| Notion Tier 1 (Governance) | https://www.notion.so/335071e361d281baaf3bffb6b57eabf4 | Policies and decisions |

---

*Last updated: 2026-04-13 | Owner: copilot (hydration pass) | Edit policy: Agent-editable*
