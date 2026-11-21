---
name: codebase-summary
description: Explore a repository and create or update a bounded, self-contained codebase guide (architecture, startup, component responsibilities, data ownership, feature flows), or answer focused questions about how the code works from trigger to outcome. Use for "document this codebase", "explain how X works", onboarding to an unfamiliar repo, or tracing a feature end to end. Not for language tutorials, architecture redesign, or diagnosing a specific failure.
---

# Codebase Summary

Explores a repository and explains it from inspected evidence. Paths are relative to this skill.

## Choose the Output

| Request | Output |
|---|---|
| "Document", "write a guide", "summarize the codebase", no format named | Create or update the guide file |
| "How does X work", "walk me through", "trace X" | Chat answer, no files |
| User says chat-only or no files | Chat answer, no files |
| Ambiguous | Chat answer first, then offer to save it as the guide |

## Start

Establish the repository, the reader, and what must be explained. Reuse earlier answers. Ask only when missing scope changes the result; find paths, entry points and conventions yourself. With no starting point, inspect enough to offer a short system map and a bounded scope.

| Task | Read |
|---|---|
| Guide structure, placement, limits, scope, updates | `references/documentation.md` |
| System structure, startup, component boundaries | `references/architecture.md` |
| Feature, request, command, event, background execution | `references/feature-flow.md` |

Companion skills, loaded only at the stage that needs them:

| Skill | Use when |
|---|---|
| `research` | Tracing behavior; separating implementation, docs and test expectations (`research/references/technical.md`) |
| `writing` | Writing a guide or a long chat explanation; skip for short follow-ups |
| `documentation` | Every guide creation or update (`documentation/references/workflow-guide.md`, `documentation/references/verification.md`) |
| `plan` | Only when the user asks to plan a change |

If a companion is unavailable, continue with this skill and its references. Companions never widen the evidence boundary.

## Fixed Rules

- **Evidence only.** Explain the repository from inspected code, config, tests and docs. No outside research, ecosystem comparisons, assumed patterns, application edits or unrelated artifacts.
- **Language.** Write in the language of the user's own request words, ignoring pasted code and logs. An explicit language request wins. Updating an existing guide keeps its language unless translation is requested. Keep identifiers, paths, symbols, commands and error text verbatim. For Indonesian, follow `writing/references/languages/indonesian.md` when available, and translate the section headings using the heading map in `references/documentation.md` (Title Case). Re-check anchors and the contents list after translating.
- **Entry points are real ones.** Libraries, CLIs, frontend apps and infrastructure repos have no server entry point. Start from exports, commands, routes, events or pipelines and say so.
- **Secrets.** Read `.env.example` and schemas, never `.env` or secret values.
- **Large repos.** A read-only subagent may run fan-out searches. Treat its findings as leads and open the cited files yourself.
- **Bounded.** One guide plus at most two deep dives (three files, defined here only). The main guide is the entry page. First pass: system map plus one or two representative flows, grouped by responsibility. Split rules are in `references/documentation.md`.
- **Diagrams.** At most one or two small Mermaid diagrams, labeled with real symbols.
- **Source-only.** Do not start services or run checks with external effects unless asked. Never claim runtime results from a source trace.

## Verify and Deliver

- Record `Inspected at: <short commit>, <date>` near the top of every guide (date only if there is no version control). Cite symbols and paths, not line numbers.
- Before delivery, open or grep every symbol cited beside a consequential claim, resolve relative links and anchors, and confirm the file count.
- Label the guide Draft (Draf in Indonesian) when an unresolved gap affects correctness, and name the gap. The Draft convention is in `documentation/references/clarifying.md`.
- Updates: diff from the recorded commit, revise only the affected sections, keep handwritten content, bump the commit.
- In chat, give the guide path and the checks actually run. Keep tool narration and offers out of the guide.
