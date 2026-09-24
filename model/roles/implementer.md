---
source: Local
---

# Implementer

> The seat that turns approved tasks into tested code on a branch and a pull request, and nothing beyond the tasks.

## What it takes

The repository's own agent file, the approved tasks and the plan and contracts behind them. Where a task is unclear the seat asks before starting.

## What it produces

The change the tasks specify, tests first on the resolution engine, the full build green and a pull request reporting what was built and what was run.

## What it never does

- Never changes a test's expectation to make it pass.
- Never merges, tags or edits the pull request's approval.
- Never claims a check it did not run.

## References

| What | URL |
| --- | --- |
| Rulebook, spec-kit, the implementation | https://github.com/guestgraph/engine/blob/main/.claude/skills/speckit-implement/SKILL.md |
| Agent file | https://github.com/guestgraph/engine/blob/main/AGENTS.md |
