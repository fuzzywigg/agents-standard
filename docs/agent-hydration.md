# Agent Hydration Report — agents-standard

> **Protocol:** REPO HYDRATION PROTOCOL v1.0
> **Generated:** 2026-04-13
> **Agent:** copilot (hydration pass)
> **Branch:** `copilot/add-hydration-feature`
> **Hydrated by:** GitHub Copilot coding agent

---

## Phase 1: Discovery — Findings Report

### Repository Identity

| Attribute | Value |
|-----------|-------|
| Repo | `fuzzywigg/agents-standard` |
| Purpose | Public-facing canonical agent operating protocol |
| Primary artifact | `AGENTS.md` v3.2.0 (1770 lines) |
| Language/framework | Markdown (documentation repo, no runtime) |
| Default branch | `alpha` |

### Findings Matrix

| Category | EXISTS | MISSING |
|----------|--------|---------|
| **Identity** | `README.md` (15L, has `[PROJECT_NAME]` placeholder), `AGENTS.md` (1770L, v3.2.0) | `LICENSE`, filled README |
| **Source architecture** | Root-only: 2 files + `.github/agents/` | `docs/`, `src/`, any structure |
| **Dependencies** | None (no package manifest) | None needed for pure docs repo |
| **Tests** | None | Markdown lint CI, link-check CI |
| **CI/CD** | None | `.github/workflows/` entirely missing |
| **Documentation** | `AGENTS.md` (comprehensive), `README.md` (minimal) | `CHANGELOG.md`, `docs/usage-examples.md` |
| **Governance** | `AGENTS.md`, `.github/agents/my-agent.agent.md` | `CLAUDE.md`, `CONTRIBUTING.md`, `SECURITY.md`, `CODEOWNERS` |
| **Templates** | None | Issue templates, PR template |
| **Security** | AGENTS.md Part 6+17 describe protocols | `SECURITY.md`, `CodeQL` scanning, `.gitignore` |
| **Runtime artifacts** | None | `agentic_flows/scratchpad.txt` (declared in AGENTS.md frontmatter), `postmortem.md` |
| **Git state** | 2 branches (`alpha`, `copilot/add-hydration-feature`), 2 commits | Branch protection, open issues, PR template |

---

## Phase 2: Question Lists

### LIST A — Resolved by Research

| Question | Answer | Source |
|----------|--------|--------|
| What format should CLAUDE.md follow? | Repo-purpose, routing matrix, branch strategy, file ownership, validation commands | Protocol requirement + AGENTS.md Part 8 |
| What license is appropriate? | MIT — open-source intent, public standards doc | AGENTS.md Part 21 ("public-facing"), README intent |
| What name fills `[PROJECT_NAME]`? | FUZZYWIGG-AI | AGENTS.md frontmatter: `owner: "FUZZYWIGG-AI Ecosystem"` |
| Should runtime artifacts be committed? | Stub/template yes; live content gitignored | AGENTS.md Part 16.2 (append-only, scratchpad semantics) |
| What CI tooling fits a pure docs repo? | `markdownlint`, `markdown-link-check` | Industry standard for Markdown repos |
| Is `alpha` the main branch? | Yes — only branch with commits, treated as default | `git branch -a` output |

### LIST B — Requires HITL (Andrew)

> 🔲 **Deferred — no blocker on Phase 4+ execution**

| Question | Why it matters | Where to find answer |
|----------|---------------|---------------------|
| Will this repo ever contain executable code (not just docs)? | Determines if we need a build system, test runner, devcontainer | Andrew's head |
| Should `postmortem.md` be committed (template) or always gitignored (runtime)? | Affects Issue 5 design | Andrew's preference |
| Which other repos should link/import from this one? | Determines cross-repo references in docs | Notion Master Index |
| Should external contributors be invited? | Determines CONTRIBUTING.md tone and scope | Andrew's preference |
| Target audience for `docs/usage-examples.md`? | Determines which LLM APIs to show examples for | Andrew's preference |

---

## Phase 3: Resolutions Applied

All LIST A questions were resolved. LIST B questions are deferred — they do not block Phase 1 or Phase 2 issue execution.

---

## Phase 4: Issues Generated

**13 issues** across **3 phases** and **2 agent surfaces** (`copilot`, `browser-claude`).

See `docs/hydration-issues.md` for the complete issue specifications.

### Phase Summary

| Phase | Issues | Surfaces | Description |
|-------|--------|----------|-------------|
| Phase 1 (Foundation) | #1–5 | copilot | LICENSE, README fix, CLAUDE.md, .gitignore, runtime stubs |
| Phase 2 (Hardening) | #6–11 | copilot, browser-claude | CI, CONTRIBUTING, SECURITY, templates, CODEOWNERS, CHANGELOG |
| Phase 3 (Optimization) | #12–13 | copilot | markdownlint config, usage examples |

---

## Phase 5: Roadmap Tracker

### Issue [claude] agents-standard Roadmap — Development Timeline & Issue Tracker

> **HITL action:** Create this as a GitHub issue with label `roadmap` after Phase 1 issues are created.

**Issue body:**

---

**Status:** ACTIVE | **Tier:** 1 | **Created:** 2026-04-13 | **Owner:** claude-cowork
**Source links:** `docs/hydration-issues.md`, `docs/agent-hydration.md`
**Edit policy:** Update as issues are closed; structural changes require Andrew approval

### Phase 1 — Foundation (P1) — Complete First

| # | Title | Surface | Status |
|---|-------|---------|--------|
| 1 | Add LICENSE | copilot | 🔲 Open |
| 2 | Fix README placeholder + expand | copilot | 🔲 Open |
| 3 | Add CLAUDE.md | copilot | ✅ Done |
| 4 | Add .gitignore | copilot | 🔲 Open |
| 5 | Runtime stubs (scratchpad, postmortem) | copilot | 🔲 Open |

**Exit Criteria:** `alpha` has LICENSE, complete README, CLAUDE.md, .gitignore, and runtime stubs. No placeholder text remains.

### Phase 2 — Hardening (P2) — After Phase 1

| # | Title | Surface | Status |
|---|-------|---------|--------|
| 6 | CI workflow (Markdown lint + link check) | copilot | 🔲 Open |
| 7 | CONTRIBUTING.md | copilot | 🔲 Open |
| 8 | SECURITY.md | copilot | 🔲 Open |
| 9 | GitHub issue + PR templates | copilot | 🔲 Open |
| 10 | CODEOWNERS + branch protection | browser-claude | 🔲 Open |
| 11 | CHANGELOG.md | copilot | 🔲 Open |

**Exit Criteria:** PRs require review, CI blocks broken Markdown, all governance docs present, security reporting path documented.

### Phase 3 — Optimization (P3) — After Phase 2

| # | Title | Surface | Status |
|---|-------|---------|--------|
| 12 | markdownlint config | copilot | 🔲 Open |
| 13 | Usage examples in docs/ | copilot | 🔲 Open |

**Exit Criteria:** CI passes cleanly with tuned lint config; external developers can onboard via usage examples.

### Dependency Graph

```
Issue 1 (LICENSE) ──────────────────────┐
Issue 2 (README) ────────────────────── ┤──► Issue 6 (CI) ──► Issue 10 (Branch Protection)
Issue 3 (CLAUDE.md) [DONE] ─────────── ┤──► Issue 7 (CONTRIBUTING)
Issue 4 (.gitignore) ──────────────────┐│
Issue 5 (runtime stubs) ◄──────────── ─┘└──► Issue 11 (CHANGELOG) ──► Issue 2 (README badge)
                                            Issue 8 (SECURITY)
                                            Issue 9 (Templates)
Issue 6 (CI) ──────────────────────────────► Issue 12 (markdownlint config)
Issues 1+2 ────────────────────────────────► Issue 13 (Usage examples)
```

### Surface Distribution

| Surface | Issues | Estimated effort |
|---------|--------|-----------------|
| `copilot` | #1-9, #11-13 (12 issues) | ~30-60 min total |
| `browser-claude` | #10 (1 issue) | ~15 min (UI navigation) |

### Governing Principles

1. Never commit directly to `alpha`
2. All AGENTS.md changes require PR + Andrew review
3. CI must pass before merge (after Issue 6 is active)
4. State residency: code/config in GitHub, policies in Notion, don't duplicate
5. Issue specs live in `docs/hydration-issues.md` — the GitHub issues reference them

---

## Phase 6: Cross-System Documentation

### GitHub (Completed in this pass)

- [x] `CLAUDE.md` created at repo root
- [x] `docs/agent-hydration.md` created (this file)
- [x] `docs/hydration-issues.md` created with all 13 issue specs
- [x] Committed and pushed to `copilot/add-hydration-feature`

### Notion (HITL Required)

> **Action for Andrew or `claude-cowork`:**
> 1. Search Master Index for `agents-standard` page
> 2. If not found: create page under "Active Sprint Work" with metadata header
> 3. Link to the GitHub roadmap issue (once created) and this hydration doc
> 4. Do NOT copy content — link to GitHub as the source of truth

### Gist

No reusable standalone artifact was produced in this hydration pass (all outputs are repo-specific). If the hydration prompt template itself becomes reusable, create a gist and link from Notion.

---

## Recommended First Action

**Start with Issue #3 → Issue #1 → Issue #2, on `copilot` surface.**

CLAUDE.md is already done (in this pass). The next highest-value action is adding LICENSE (Issue #1) — it unblocks external adoption which is the entire purpose of a public standards repo. Issue #2 (README) immediately follows to clean up the placeholder.

Once Phase 1 is complete, route Issue #10 (branch protection) to `browser-claude` in parallel with Issue #6 (CI) on `copilot`.

---

*Generated by hydration pass | 2026-04-13 | copilot agent surface*
