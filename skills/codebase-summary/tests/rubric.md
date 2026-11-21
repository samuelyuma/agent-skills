# Codebase Summary Review Rubric

Evaluate the generated documentation, delivery message, inspected evidence, questions, companion-skill reads, and tool actions together.

| Dimension | Pass Condition |
|---|---|
| Scope | Documents the requested system and selected flows without unrelated artifacts, application changes, language lessons, or comparisons; covered and deferred areas are clear |
| Deliverable | Creates or updates a self-contained guide by default, honors explicit chat-only questions, and links the artifact in its delivery message |
| Reader Boundaries | Starts with one guide, splits only for coherent deep dives within the default three-file ceiling, groups sources by responsibility, and prioritizes representative flows rather than cataloging every file |
| Navigation and Updates | Keeps the main guide as the entry page, verifies source/page links, avoids duplicated detail, and updates the same pages on follow-ups |
| Grounding | Consequential claims follow inspected repository evidence with useful file or symbol references; scope and missing evidence are visible |
| Architecture | Identifies responsibilities, relevant entry points, actual wiring, dependency direction, and state ownership without imposing a pattern |
| Flow | Connects the selected trigger to outcome in execution order, including meaningful data movement and state changes |
| Boundaries | Distinguishes immediate results from background continuation and supported behavior from unknown external internals |
| Evidence Types | Separates implemented behavior, documented intent, architectural interpretation, unrun test expectations, and runtime observations |
| Interaction | Reuses user choices, resolves consequential scope questions, and delivers the guide rather than leaving required explanations across chat turns |
| Consistency | Uses the shared document structure when relevant, with stable terminology, a coherent reading order, and substantive connected explanations |
| Reuse | Loads available `research`, `writing`, and `documentation` for guide creation or updates; loads `plan` only for requested change planning; does not copy their full workflows |
| Independence | Produces useful documentation without companion skills or external lookup; essential behavior remains inside the installed skill |
| Verification | Reports only actual execution, names incomplete traces, and keeps trial artifacts outside the skill package |
| Language | Writes in the language of the request (explicit request first, existing guide language on updates), translates headings, and keeps identifiers, paths, symbols, commands, and error text verbatim |
| Freshness | Records the inspected commit and date, cites symbols rather than line numbers, verifies cited symbols before delivery, and updates by diffing from the recorded commit |

Fail invented connections or guarantees, false test or runtime claims, unexplained documentation conflicts, secret inspection, unrequested application edits, chat notes substituted for a requested guide, uncontrolled page growth, or explanations driven by an assumed language or architecture. Installing successfully proves discovery, not documentation quality.

Record the request, raw artifacts, generated answer, relevant tool actions, and scenarios actually exercised. For companion-skill reuse, an observed read or invocation is required; saying a skill was used is insufficient evidence.
