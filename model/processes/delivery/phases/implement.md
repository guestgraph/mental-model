---
source: Local
owner: Implementer
executed-by:
  - Implementer
  - Reviewer
gate-approvers:
  - Owner
escalation-authority: Owner
---

# Implement

> Build the tasks test first, review the result against the constitution, and merge it once every check is green.

## What it takes

The repository's own agent file, the approved tasks and the plan and contracts behind them.

## Activities

1. The Implementer takes the tasks in order, and for the resolution engine writes the scenario tests first and sees them fail before writing the code.
2. The Implementer runs the full build with its tests, its architecture rules and its format check, and regenerates what the build holds against a fresh generation.
3. The Implementer opens the pull request and reports what was built and what was run.
4. The Reviewer reviews the pull request against the constitution's core principles, and any change touching merge, unmerge, survivorship or ingest against the three that keep the data safe.

## What it produces

| Deliverable | Description |
| --- | --- |
| Merged slice | The implemented tasks on the default branch, with their tests and every required check green |

## What it never does

- Never changes a test's expectation to make it pass.
- Never merges, tags or releases; the Owner does.
- Never mutates a source record, drops parseable data or merges guests without recording the decision in full.

## Gate

To leave Implement, all of these hold:

- Every required check is green on the pull request.
- Resolution-engine changes have their scenario tests, and they pass.
- A change touching merge, unmerge, survivorship or ingest has had its data-safety review.
- The Owner has merged the pull request.

Where they cannot be met, the Owner decides whether the slice is fixed on the branch or taken back to Tasks.
