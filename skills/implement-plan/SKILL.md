---
name: implement-plan
description: >-
  Implements existing Markdown plans exhaustively through delegated task loops,
  validation, and review closure. Use this skill when asked to implement,
  execute, carry out, or continue an existing plan. Do not use for creating a
  plan from scratch or only reviewing a plan without implementing it.
license: MIT
compatibility: >-
  Requires project write access. Delegation requires a safely available
  subagent capability. Browser-visible work requires browser automation.
metadata:
  short-description: Implement plans via delegated task loops and review
---

# Implement Plan

## Rules

- Stay within the plan's required outcome; research/review does not add scope. Prefer the smallest sufficient change.
- Delegate when safe under `use-subagents`; small size alone does not justify skipping. Parent owns the work document, ADR status, integration, dispositions, acceptance, and cleanup.
- Child claims and review findings are evidence, never automatic acceptance or new work. Inspect diffs and rerun relevant checks.
- Material unresolved scope/risk choices or stalled review (two failed rounds, recurrence, or no progress) → ask user. Honor existing authorization.

## Startup and resume

1. Read [ADR conventions](../create-plan/references/adr-conventions.md), the full plan/work document, and relevant accepted ADRs. Resolve material conflicts before dependent implementation.
2. Read [implementation updates](assets/implementation-updates.md). Apply missing fields to the existing work document; preserve task IDs, requirements, and evidence. Reconcile current state instead of creating another tracker.
3. Map every actionable requirement to a task/subtask with acceptance checks. An ADR alone is not an executable plan: use `create-plan` when a plan is missing.
4. Only then implement. Missing required resources → stop.

## Task loop

For each dependency-ready task, delegate by default:

1. **Analyze** starts-at files, callers, and tests. Use `web-research` for uncertain external behavior; keep findings in the same work document.
2. **Implement** the smallest sufficient change within ownership. Record deviations; material decision changes follow the ADR lifecycle.
3. **Check** targeted tests and applicable lint/typecheck/build/migration/browser checks (`agent-browser` for UI).
4. **Review** with independent adversarial `code-review` at plan checkpoints and real boundaries: integration, migration, public contracts, security/data invariants, risky dependencies, or completed batches. Always review the final full plan.
5. **Disposition** each finding: `Fix now` / `Validate` / `Reject` / `Ask user` / `Block`. Fix accepted items, rerun checks, and re-review affected scope until `Clear`. Complexity-increasing fixes → `decomplex` triage or a disclosed built-in gate; material doubt → ask user.
6. **Update** task status/evidence and next action in place. `Verified` needs evidence; `Descoped` needs user authorization. Link separate review reports and concise closure.
7. **Clean up** lane resources under `use-subagents`, then continue.

Parallelize independent tasks with isolated writers. Parent alone updates shared work and ADR status. Use fresh reviewers without sharing prior conclusions; one reviewer by default. If independent review is unavailable, disclose the parent-review limit.

## Finish

1. Reread the full plan and relevant ADRs; reconcile every requirement and remove unjustified scope/complexity.
2. Complete final checks and plan-backed implementation review; use `decomplex` Audit when proportionate. Challenge completion against implementation and validation evidence, not task labels alone.
3. Clean up workflow-owned worktrees, branches, processes, and runtime state; document retained resources and reasons.
4. Mark `Complete` only when every task is `Verified` or approved `Descoped`, validation passed, final review is `Clear`, and nothing material remains open. Otherwise use `Partial` or `Blocked`.
5. Deliver the work-document path, related ADRs/reviews, status and remaining IDs, changes, checks run/skipped, review dispositions, delegation limits, and retained resources. HTML reports are optional requested deliverables, not a completion gate.
