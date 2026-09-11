---
name: web-research
description: Researches current web and external technical information through source-backed discovery, retrieval, and repository, document, or media inspection. Use this skill when the user needs current facts, docs, articles, URLs, repositories, PDFs, videos, comparisons, or version-specific library/API/framework evidence. Do not use this skill alone for interactive browser tasks such as login, forms, or UI-state inspection; use an available browser automation capability.
license: MIT
compatibility: >-
  Requires at least one current search, content-retrieval, repository, document,
  or media capability appropriate to the task. Interactive login, form, or UI
  state workflows additionally require an available browser automation
  capability.
metadata:
  short-description: Research current web, code, repository, document, and media evidence
---

# Web Research

## Rules

- Honor user constraints, including no-write/chat-only requests. Discover available retrieval capabilities; do not assume tool names.
- Prefer primary sources and read answer-critical content. Search snippets and generated summaries are discovery aids, not sufficient evidence.
- For dependency claims, establish installed/targeted versions and runtime/integration boundaries. Prefer version-matched source over conflicting live documentation.
- For signatures, hashing, serialization, canonicalization, authentication, or wire protocols, require an independent official implementation, test vector, or interoperability check; self-consistent round trips are insufficient.
- Cite URLs, separate observation from inference, and state uncertainty. Never store secrets, credentials, private sessions, or sensitive source content.

## Resources

Read before the corresponding work:

| Work | Resource |
|---|---|
| Substantial research notes or decision synthesis | [ADR conventions](../create-plan/references/adr-conventions.md): shared document paths and decision authority |
| Complex, filtered, multi-angle, or current discovery | [Web search](references/web-search.md) |
| Multiple sources, repositories, PDFs, or truncated content | [Content retrieval](references/fetch-content.md) |
| Video/audio or visual moments | [Media](references/media.md) |

Use browser automation for logins, forms, or dynamic interaction; local parsers/screenshots for local documents.

## Workflow

1. **Frame.** Small direct lookups need no artifact. For substantial, conflicting, resumable, implementation-critical, or high-risk research, read ADR conventions and reuse the active work document or create `adrs/work/<research-slug>.md`. Record question, scope, constraints, known context, and search angles. No-write → retain evidence in the response.
2. **Establish context.** Inspect manifests, lockfiles, configuration, or exact source when applicable. Identify the behavior, compatibility, failure, and integration questions that affect the answer.
3. **Discover.** Inspect user-supplied sources first; otherwise use two to four distinct angles, such as official docs, source/release history, and corroborating implementations. Retrieve selected answer-critical sources.
4. **Inspect.** Read actual docs/source/tests or media. Resolve truncation through full content or an alternate retrieval path. In substantial research, retain useful findings, citations, version/date scope, material conflicts, rejected evidence, open questions, and next action in the same work document.
5. **Resolve.** Assess authority, directness, version match, and failure behavior. Follow up narrowly on material gaps; stop when supported, remaining gaps are non-material, or further useful evidence is unlikely.
6. **Synthesize.** Reread existing work notes before final responses, handoffs, or compaction. State findings, implications, source conflicts, and limits. Link decision-relevant evidence to the owning ADR; draft only actual significant choices and never treat research as acceptance. Reusable technology knowledge belongs in the wiki.

Late results warrant a follow-up only if they materially change the conclusion or the user asks.
