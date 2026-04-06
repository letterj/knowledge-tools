# Runbook

Development journal for knowledge-tools. Tracks progress, project plans, features, tasks, and decisions.

---

## Project Status
Active — initial setup

## Current Focus
Repository initialization and security tooling

---

## Task List

### In Progress
- [ ] Initialize local git repo
- [ ] Verify gitleaks pre-commit hook
- [ ] Push initial structure to github.com/letterj/knowledge-tools

### Backlog
- [ ] First automation tool — raw/ ingestion script
- [ ] First health check tool — wiki contradiction detection
- [ ] lib/ shared utilities — path resolution, file I/O helpers
- [ ] Evaluate Gemini CLI integration (GEMINI.md)

---

## Decisions

| Date | Decision | Rationale |
|------|----------|-----------|
| 2026-04-05 | Public repo | Open by default; gitleaks blocks secrets at commit time |
| 2026-04-05 | gitleaks for secret scanning | Purpose-built, actively maintained, pre-commit integration |
| 2026-04-05 | Keep a Changelog format | Standard, readable, tooling-friendly |
| 2026-04-05 | Local-first git workflow | Build locally, review, then push — every interaction |

---

## Notes
- Development machine: MacBook M2, 32GB RAM, macOS Tahoe 26.3 (beta)
- Primary local tool: Claude Code
- Potential future tool: Gemini CLI (document in RUNBOOK when adopted)
- macOS Tahoe 26.3 is beta — watch for unexpected behavior in git hooks and tooling
