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

---

## Project Plan

### 1. Create CLAUDE.md in knowledge-tools Repo
Set up the Claude skills instruction file at the root of the `knowledge-tools/` repo. This file defines how Claude behaves when working inside this project — conventions, file responsibilities, and skill definitions.

**Skills to define:**
- `morning-sync` — syncs local repo with origin/main on GitHub
- `create-issue` — creates a GitHub issue for items in the project plan
- `create-pr` — creates a pull request tied to an open issue
- `update-docs` — updates CHANGELOG.md, README.md, and RUNBOOK.md after a commit
- `code-review` — reviews pull requests for correctness, style, and test coverage

**Status:** Pending

---

### 2. Set Up the Knowledge Base
Initialize the knowledge base directory structure on iCloud Drive and verify CLAUDE.md is in place and correct.

    ~/Library/Mobile Documents/com~apple~CloudDocs/Documents/knowledge-base/
      CLAUDE.md
      raw/
      wiki/
      outputs/
      _archive/

**Status:** Pending

---

### 3. Load First File into Knowledge Base
Load the first source document into raw/:

- **File:** ideas_lunar_economy.pdf
- **Destination:** raw/ideas_lunar_economy.pdf
- **Next step:** Run initial wiki compile prompt against this file

**Status:** Pending

---

### 4. Implement Issue/PR Workflow (Active Development Gate)
Before active tool development begins, establish the GitHub Issue and Pull Request workflow. No feature work starts without an open issue. No merge happens without a PR and code review.

**Workflow:**
1. Create issue via `create-issue` skill
2. Create feature branch tied to issue
3. Develop locally
4. Run ruff and pytest before committing
5. Push branch
6. Create PR via `create-pr` skill
7. Run code review via `code-review` skill
8. Merge to main
9. Update docs via `update-docs` skill
10. Morning sync via `morning-sync` skill at start of next session

**Status:** Pending — activate when first tool development begins

---

### 5. Create Claude Skills (CLAUDE.md)
Define the following skills in CLAUDE.md at the repo root:

| Skill | Description |
|-------|-------------|
| `morning-sync` | Pull latest from origin/main, report any changes, flag conflicts |
| `create-issue` | Create a GitHub issue with title, description, and labels |
| `create-pr` | Create a pull request linked to an open issue |
| `update-docs` | Update CHANGELOG.md (Keep a Changelog), README.md (operational changes), RUNBOOK.md (progress and decisions) after every commit |
| `code-review` | Review pull requests for correctness, test coverage, ruff compliance, and adherence to project conventions |

**Status:** Pending — see Project Plan item 1
