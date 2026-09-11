---
name: decomplex
description: >-
  Reviews proposed or existing work for unnecessary complexity and triages
  complexity-increasing recommendations without editing the reviewed targets.
  Use this skill when asked to simplify or decomplex source, tests,
  configuration, dependencies, plans, designs, or architecture; challenge
  over-engineering; audit unnecessary complexity; or triage recommendations
  that would add complexity. Do not use for general defect review,
  implementation or fixes, style-only cleanup, or conceptual explanations that
  need no durable review report.
license: MIT
compatibility: >-
  Requires read access to reviewed targets and project write access for one
  adrs/work/ report; has no hard runtime dependency and never writes targets.
metadata:
  short-description: Evidence-gated complexity prevention, audit, and triage
---

# Decomplex

## Hard rules

- Exactly one mode:
  - **Prevention** — unimplemented plans/designs/deps/safeguards
  - **Audit** — existing source/tests/config/deps/architecture
  - **Finding triage** — supplied recs that may add complexity
- Fix before reviewing:
  - target
  - authority
  - required behavior
  - scope
- Ask only when ambiguity changes those.
- Targets immutable.
- Before fixing the contract, read [ADR conventions](../create-plan/references/adr-conventions.md) for paths and decision authority.
- **Only** write: one `adrs/work/<change>-decomplex.md` unless an explicit output path overrides it.
- Never edit reviewed artifacts (even if asked to fix).
- Honor explicit no-write/chat-only requests with findings in chat. If a requested file cannot be written, disclose the limit; never claim it was saved.
- Complexity trade-offs only.
- Route defects/security/perf/plan-compliance to the owning workflow (e.g. `code-review`).
- Simplicity ≠ fewer lines/helpers/deps.
- Preserve evidenced:
  - trust boundaries
  - invariants
  - compatibility
  - lifecycle cleanup
  - ops needs
- Findings are advisory.
- Consumer dispositions/implements/escalates.
- **“No potential complexity findings” is valid.**
- Consumers must:
  - disposition every item
  - never auto-implement
  - **ask user** when in doubt

## Admission gate (all required)

1. Concrete conceptual, maintenance, or operational burden
2. Absent/insufficient justification for current need
3. Realistic, reachable practical cost
4. Smallest concrete simpler alternative
5. Required behavior preserved
6. Proportionate value after simplification + regression cost
7. Explicit exception/boundary check

Evidence:

- `Confirmed` or `Supported` only

If the gate fails:

- bounded validation
- user question
- or omit

Never find on:

- helper count
- duplication alone
- novelty
- hypothetical scale
- style alone

Prefer:

1. delete
2. direct use
3. local logic/helper
4. existing shared abstraction
5. new abstraction

## Sequence

1. **Contract**
   - read ADR conventions and relevant accepted decisions
   - mode
   - target
   - authority
   - scope
   - behavior
   - report path
   - constraints
   - inspect callers/tests/config/history only as needed for the gate
2. **Before candidates**
   - read [`references/complexity-gates.md`](references/complexity-gates.md) fully
   - contextual signals, not a quota checklist
3. **Evaluate**
   - full gate each candidate
   - order by expected simplification value
4. **Recommend**
   - only: `Act` | `Validate` | `Ask user`
   - do not perform the action
   - triage mode: preserve every supplied ID
   - triage dispositions: `Act` | `Validate` | `Ask user` | `No action`
5. **Before write**
   - read [`assets/decomplex-review-template.md`](assets/decomplex-review-template.md) fully
   - write exactly one report, or return it in chat under no-write constraints
   - strip template guidance/empty sections
   - keep inspected/skipped coverage + limitations
6. **Verify**
   - requested report exists, or chat-only delivery/limit is explicit
   - admitted items pass gate
   - all triage IDs accounted
   - no target file changed
