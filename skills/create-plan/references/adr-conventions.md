# ADRs and supporting work

Read before selecting artifact paths or interpreting decision authority. Explicit user/repository paths override these defaults; reuse the current work document and never migrate unrelated files automatically.

## Files

- `adrs/NNNN-<decision>.md`: one significant decision and its rationale. Allocate the next unused number; never renumber published records or reuse IDs.
- `adrs/work/<change>.md`: one mutable document for research, plan, task status, evidence, blockers, and next action. Preserve task IDs and useful evidence on resume; update existing sections instead of appending duplicate plans/trackers.
- `adrs/work/<change>-review.md` and `<change>-decomplex.md`: separate review reports, created only when needed. Keep full findings there; link dispositions/closure from the work document. Give distinct review scopes distinct filenames.
- Decision-related HTML reports may use `adrs/work/<change>-report.html`; honor explicit deliverable paths.
- Work may reference zero, one, or several ADRs. Routine fixes and research need no invented decision. Keep reusable technology knowledge in the wiki.
- Parent owns the shared work document and ADR status; reviewers do not edit their targets. No-write requests return findings in chat.

## Decisions and authority

- Read relevant accepted ADRs before planning, implementation, or compliance review. Follow explicit user instructions and existing authorization; surface material conflicts with the plan instead of silently choosing an authority.
- Draft significant new choices as `Proposed`. Mark `Accepted` only when supported by the user's authorization or established project decision process; reviewer `Clear` alone is not acceptance. Do not request approval already given.
- Decision states: `Proposed`, `Accepted`, `Rejected`, `Deprecated`, `Superseded`. Acceptance does not mean implementation is complete; track execution in the work document.
- Preserve accepted/rejected rationale. A material change needs a new ADR; once accepted, link it from the superseded record. Clerical corrections and lifecycle links may be updated in place.
- Keep records short (usually one or two pages). Capture realistic alternatives and actual trade-offs, not task logs or fabricated history.

## ADR shape

When creating an ADR, reuse `adrs/template.md` if present; otherwise use this shape. Omit unhelpful optional sections; an additional template file is optional.

```markdown
# ADR-NNNN: <Decision title>

- Status: Proposed
- Date: YYYY-MM-DD

## Context
Problem and constraints.

## Decision
Choice and rationale.

## Alternatives considered
Real alternatives and why they were not selected.

## Consequences
Benefits, costs, limitations, and obligations.

## Confirmation
How compliance will be checked. Optional.

## References
Evidence, related ADRs, and supporting work. Optional.
```
