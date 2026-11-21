# Codebase Guide

## Choose the Scope and Destination

Write for a reader who wants to understand how the inspected system works without needing the chat history. Preserve an explicitly requested scope, format, or destination. Otherwise inspect existing documentation and update the maintained guide that serves this purpose. If none exists, follow the repository's documentation placement or use `docs/codebase-guide.md` when no convention exists.

State the covered application or subsystem and the selected flows near the beginning. In a multi-application repository, establish the relevant system connections before choosing where to go deep. Ask a focused question when several selections would produce materially different guides. If asked to proceed without questions, choose a defensible bounded first pass, state that scope, and identify deferred areas.

The default first pass covers the system map and one or two representative flows. A flow should reveal meaningful component boundaries, data movement, or state changes relevant to the user's goal. Inspect their implementations deeply enough to explain them; group the remaining areas by responsibility and identify them as outside the detailed coverage. A short guide must still explain the connections, not replace them with a file list.

## Bound the Reading and Output

Use the single-guide default and three-file ceiling defined in `SKILL.md`. The ceiling counts the main guide and any deep dives, including navigation or appendix pages created for this guide; it does not require removing existing repository documentation. Keep diagrams inline when useful rather than creating an asset collection.

Split only when a substantial topic has its own coherent reading purpose and retaining it would interrupt the main guide. Keep a useful summary and a link in the main guide, and a return link in each deep dive. Keep the detailed explanation in one place. A large number of source files is not sufficient reason to split; explain their shared responsibility together.

When more topics would require exceeding the file ceiling, state the coverage tradeoff and ask the user to prioritize or explicitly expand it. While waiting, complete independent sections within the existing boundary. Do not silently grow the collection or discard requested detail to satisfy a number. If more pages are explicitly requested, preserve a single entry page and extend navigation deliberately.

Start source inspection with project definitions, startup, and the selected flows. Follow relevant callers, wiring, state access, and tests rather than reading every source file. Treat generated, vendored, or unrelated areas as leads only when the trace depends on them. Resolve through maintained inputs or visible adapters where possible and name unsupported transitions. The stopping condition is a supported system map and selected flow coverage, not an arbitrary source-file quota or exhaustive traversal.

## Document Structure

Use this order for a new guide, adapting depth and omitting inapplicable sections. Preserve useful structure in existing guides. Keep one title and a compact linked contents list when the guide is long enough to need navigation.

1. **Purpose and Scope.** Explain what the system does, who or what uses it, the covered areas and flows, and consequential exclusions. Record `Inspected at: <short commit>, <date>` here (date only without version control).
2. **System Structure.** Group important areas by responsibility and explain their connections. Include a small source map only where it helps readers navigate.
3. **Startup and Initialization.** Trace the relevant starting points and the wiring that assembles runtime components.
4. **Architecture and Data Ownership.** Explain boundaries, dependency direction, communication, state ownership, and meaningful persistence boundaries. Attribute documented design intent rather than inventing rationale.
5. **Feature Flows.** Give connected, numbered walkthroughs of the selected triggers through outcomes. Cover material branches, failures, and background continuation where evidenced. Link a deep dive when one is justified.
6. **Configuration and Integrations.** Explain inspected configuration names and external boundaries that change the described behavior; keep secret values out.
7. **Open Questions.** Preserve consequential missing bindings, documentation conflicts, and unsupported guarantees. Put a limit next to the affected explanation as well when needed for accuracy.

Heading map for guides written in Indonesian (keep Title Case, and keep headings of an existing guide as they are):

| English | Indonesian |
|---|---|
| Purpose and Scope | Tujuan dan Cakupan |
| System Structure | Struktur Sistem |
| Startup and Initialization | Startup dan Inisialisasi |
| Architecture and Data Ownership | Arsitektur dan Kepemilikan Data |
| Feature Flows | Alur Fitur |
| Configuration and Integrations | Konfigurasi dan Integrasi |
| Open Questions | Pertanyaan Terbuka |

Write substantive connected prose within each section, with code excerpts, tables, or diagrams only when they clarify actual relationships. Explain a repository term when necessary to understand its role. Avoid per-file chapters, repeated directory trees, empty boilerplate, syntax tutorials, and imported architecture assumptions. Explicitly separate an expected or documented outcome from what implementation establishes.

## Update and Verify

For follow-up documentation requests, update the same guide or relevant existing deep dive instead of creating another summary per issue or conversation. Diff the repository from the recorded `Inspected at` commit to find affected sections, revise only those, bump the recorded commit, and preserve correct explanations, handwritten additions, and useful source links. For an explicitly chat-only follow-up, answer without changing files; do not expand into unrelated sections.

Resolve file links relative to the final document's location and verify heading anchors and reciprocal page links. Reference symbols and paths rather than line numbers near consequential claims, and before delivery open or grep each cited symbol to confirm it still exists. Check that the main guide explains the system without requiring the reader to open every supporting page. List deferred coverage honestly rather than claiming exhaustive understanding.

Use the available `documentation` verification workflow and `writing` document guidance. Keep inspection logs, validation-command results, and conversational offers in the delivery message. Explain essential uncertainty inside the guide; label it Draft when an unresolved gap affects its correctness or usability. A source-based guide must not imply the application or its tests were run.
