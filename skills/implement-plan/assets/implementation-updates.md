# Implementation updates

Apply these fields to the existing work document. Preserve its task IDs, requirements, and evidence; do not copy tasks into a second tracker. Add only missing fields/sections and remove unused placeholders.

## Document fields

- **Status:** `In progress` | `Partial` | `Blocked` | `Complete`
- **Updated:** YYYY-MM-DD
- **ADRs:** Relevant decision links, or None

## Per existing task/subtask

- **Status:** `Pending` | `In progress` | `Blocked` | `Verified` | `Descoped`
- **Evidence:** Commands/results, inspected paths, and relevant review links

`Verified` requires acceptance evidence. `Descoped` requires user authorization. Add stable subtask IDs only for independently actionable requirements.

## Handoff

- **Next action:** Next task/blocker, or None when complete
- **Reviews:** Report/checkpoint, reviewer, finding IDs, dispositions, closure
- **Deviations:** Change, rationale, authorization, and related ADR
- **Resources:** Worktree/process ownership and cleanup; retained resources with reasons

`Complete` requires all tasks verified or approved descoped, validation passed, final plan-backed review clear, and no material open work. Otherwise use `Partial` or `Blocked`.
