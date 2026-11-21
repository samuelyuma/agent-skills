# Codebase Summary Cases

Maintainer scenarios, not runtime instructions. Give an independent evaluator the skill, request, and raw artifacts without this file or the rubric. Fixtures contain invented pseudocode and repository evidence, not trial-project material. Materialize artifacts in an isolated workspace when needed. Record only scenarios actually exercised. Keep real trial repositories, prompts, outputs, and feedback outside this skill.

| ID | Scenario | Observable Success |
|---|---|---|
| C01 | Explicitly ask for a chat-only architecture overview using `fixtures/queued-work.md` | Explains purpose, inspected entry points, responsibilities, and connections without creating documentation files |
| C02 | Trace job submission to completion using `fixtures/queued-work.md` | Connects route, dispatch registration, handler, transaction, reply, poller, and worker; distinguishes acceptance from completion |
| C03 | Ask whether the same fixture sends email before replying | Preserves the README conflict; explains the implemented enqueue-and-return path and delayed worker effect |
| C04 | Ask whether delivery is exactly once from the same fixture | Names missing retry, acknowledgement, and delivery evidence rather than inventing a guarantee |
| C05 | Ask for a walkthrough using `fixtures/batch-tool.md` | Adapts to a batch entry point and file output without imposing a server, queue, database, or layered architecture |
| C06 | Ask about failure with an empty input using `fixtures/batch-tool.md` | Explains the inspected early exit and absence of a write on that branch |
| C07 | After an overview, select background processing and request only that part | Carries the selection forward, inspects the consumer path, and avoids repeating the interview or the whole map |
| C08 | Explain that a transition is still confusing | Explains the unresolved connection using a smaller piece of evidence, without a syntax lesson or unrelated analogy |
| C09 | Request a guide with `research`, `writing`, and `documentation` available at installed paths | Reads their instructions and matching references; creates a self-contained guide grounded in repository evidence |
| C10 | Make companion skills unavailable | Completes the walkthrough directly, with useful evidence and no demand to install another skill |
| C11 | Request codebase documentation without naming a file or output format | Creates one Markdown guide in the existing documentation location, or `docs/codebase-guide.md` when no convention exists; chat links to the artifact |
| C12 | Request a guide despite an apparent improvement opportunity | Documents current behavior without redesigning, patching application code, or invoking change planning |
| C13 | Explicitly request a change plan after the explanation, with `plan` available | Loads `plan` and hands off established current behavior; does not implement the change |
| C14 | Supply a known language or a trial-project name incidentally | Keeps explanations on architecture and behavior; introduces no language comparisons or assumed project pattern |
| C15 | Supply an unrun test and inaccessible binding implementation | Reports the expectation and unresolved link; claims neither test success nor a completed runtime trace |
| C16 | Ask a narrow follow-up or request no further questions | Answers directly with consistent terminology and evidence; omits unnecessary full-template repetition or next-focus questions |
| C17 | Request a whole-repository explanation in a multi-application workspace | Bounds inspected coverage and explains relevant application connections without claiming exhaustive understanding |
| C18 | External lookup is available but repository evidence has a gap | Names the gap and stays within repository evidence rather than importing an external architecture assumption |
| C19 | Supply `fixtures/large-workspace.md` alongside the queued-work evidence and request a first-pass guide | Groups related sources by responsibility, scopes detailed coverage to representative flows, and avoids one page per source file, directory, or application |
| C20 | A guide already has its main page and two deep dives; a new broad request would exceed that boundary | Updates relevant existing pages and asks a focused scope question before expanding beyond the ceiling unless more pages were explicitly requested |
| C21 | Request deeper documentation after a guide already exists | Updates the same maintained guide or relevant deep dive, preserves useful content, and creates no per-issue summary |
| C22 | Request exhaustive documentation of a repository with many applications and unclear priorities | Explains the coverage tradeoff and asks which system or flows to prioritize rather than silently claiming complete coverage or generating a document collection |
| C23 | A substantial topic earns its own deep dive | Keeps the overview in the main guide, adds reciprocal links, avoids duplicating detailed explanations, and stays within the default three-file ceiling |
| C24 | Generate a guide below a nested documentation directory | Verifies source links relative to the final page and checks contents anchors; useful source references resolve |
| C25 | Request documentation with all companion skills unavailable | Still creates a substantive guide using the bundled documentation reference; absence of companions does not turn the deliverable into chat notes |
| C26 | Explicitly authorize a larger documentation set | Honors the requested scope and navigation while keeping one entry page; the default ceiling does not erase explicit requirements |
| C27 | Ask "Why does this request return 500?" | Skill does not trigger as a guide task; no guide file is created |
| C28 | A guide records an older `Inspected at` commit and the repository has changed | Diffs from the recorded commit, updates only affected sections, bumps the commit |
| C29 | Indonesian request in a repository with English-only code and docs | Guide in Indonesian, identifiers in English, headings follow the heading map, contents list and anchors resolve |
| C30 | English request to update an existing Indonesian guide | Guide stays Indonesian unless translation is requested |
| C31 | Indonesian question that includes a pasted English stack trace | Reply in Indonesian, trace left untouched |
| C32 | Indonesian request that says to write the guide in English | The explicit language request wins |
| C33 | Use `fixtures/react-app.md` and ask for a walkthrough | Traces the UI event to the rendered outcome; separates optimistic state from the confirmed server result; invents no backend behavior |
| C34 | Library with no server or main entry | Starts from the public exports; invents no startup path |
| C35 | The guide cites a symbol that was renamed | The pre-delivery symbol check catches it and the guide is corrected |

Review the generated guide, delivery message, companion-skill reads, and other tool actions with `rubric.md`. Compare selected prompts against a previous skill snapshot or without the skill using the same raw artifacts. Judge usefulness and correctness rather than exact wording or heading count.
