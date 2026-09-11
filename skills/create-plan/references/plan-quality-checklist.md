# Plan Quality Checklist

Complete before final delivery and after material revisions. Evidence required—not intent.

## Scope and evidence

- [ ] Outcome, problem, in-scope behavior, material non-goals, approach are clear and unambiguous
- [ ] No shaky assumptions: material ambiguity was asked of the user or marked as an open gate / Blocked
- [ ] Relevant accepted ADRs and key planning files are linked with their impact; material authority conflicts resolved or gated
- [ ] Implementation starting points included without exhaustive file inventories
- [ ] External claims use inspected, authoritative, version-matched sources
- [ ] Material findings map to a decision, task, check, non-goal, or open gate

## Delegation and readiness

- [ ] Research/review was delegated by default when safe, or a recorded strong parent-only reason exists (not “small/easy”)
- [ ] Template loaded and adapted; guidance/placeholders/empty optionals removed
- [ ] `Ready` only if no unresolved material gate can change implementation; else `Blocked`
- [ ] Every stable-ID task has **Change** as concrete bullets (not a prose blob), non-exhaustive starts-at, and exact verify + expected signals
- [ ] Every changed observable behavior and applicable material risk has proportionate protection in an existing/planned test path or a justified alternate check; the selected layer observes behavior rather than implementation details
- [ ] Flat tasks unless real phase boundaries; no repeated problem/approach/check across sections
- [ ] Final acceptance covers repo gates, end-to-end checks, skips, operator steps, deferrals
- [ ] Every task challenged for a smaller alternative; no speculative scope or machinery

## Complexity, review, delivery

- [ ] Structural choices got `decomplex` Prevention or built-in gate + recorded fallback
- [ ] Consequential draft got independent review (or parent checklist + independence limit); review evidence shows material assumptions and false-green acceptance were challenged, not just checklist completion
- [ ] Every finding/rec dispositioned (`Accept`/`Validate`/`Reject`/`Ask user`/`Block`); nothing auto-applied
- [ ] Complexity-increasing accepts got triage or built-in gate; doubt escalated to user
- [ ] Focused re-review until all commissioned reviewers `Clear` (or user escalation after stall)
- [ ] Full review findings kept in separate reports; work document links concise dispositions/closure
- [ ] Existing work document reused, or saved as `adrs/work/<change>.md` unless explicitly overridden/no-write; task IDs and useful evidence preserved
- [ ] Significant new decisions have separate ADRs; acceptance has authorization evidence and is distinct from implementation status
- [ ] Delivery reports path, decisions/gates, fallbacks, review closure, risks
