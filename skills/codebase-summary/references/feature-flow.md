# Feature Flow Exploration

## Choose the Boundary

Identify the feature's trigger, inputs, and observable outcome from the user's request and repository evidence. A trigger may be a user action, request, command, event, timer, or another mechanism found in the implementation. Reuse a feature already selected in the conversation.

If no feature is selected, use the system map to identify representative choices within the guide's scope. Ask when the selection materially changes the investigation; otherwise select a bounded first pass and state its coverage. Avoid choosing an unrelated feature merely because its entry point is easy to find.

## Trace the Connections

Follow the main path in execution order. At each relevant transition, inspect the caller and target or the wiring that connects them. Record the triggering input, responsible symbol, meaningful decision, outgoing information, state change, and result where applicable.

Use the mechanisms present in the repository. Inspect registration, routing, binding, dispatch tables, configuration, or generated-code inputs when a direct call is absent. An interface, event name, or handler class alone does not prove that execution reaches it. When the binding cannot be inspected, name the unresolved transition and continue only as a conditional path.

Follow persistence through the point that performs or commits the write where visible. Separate an in-memory change, pending work, and a durable result. Follow the result back to its caller or output boundary. If an external implementation is unavailable, explain the visible call and stop claims at that boundary.

Complete the source trace when the selected trigger is connected to its outcome and consequential transitions have evidence, or identify the exact links that prevent completion.

## User Interface Flows

For a frontend trigger, trace the event handler, the state update, any request and its response, and the render that shows the result. Separate an optimistic or local UI state from a result confirmed by the server, and name where a failed request rolls back or reports an error. Follow shared state (store, cache, context) only as far as the selected flow reads or writes it.

## Branches and Background Work

Explain the successful path first, then failure or alternate paths that materially affect the requested behavior. Identify where validation, short-circuiting, rollback, or error propagation is implemented when relevant. Do not infer behavior merely from a test name or a customary framework convention.

For asynchronous continuation, inspect the producer, handoff mechanism, consumer registration, consumer implementation, and completion or failure handling where available. Distinguish an immediate acknowledgement from later processing and effects. State what is known about ordering, retries, delivery, and transaction boundaries only when inspected evidence establishes it.

## Present the Walkthrough

Use the guide structure in `references/documentation.md` or the focused chat order in `SKILL.md`, according to the requested output. Keep selected flows together in the main guide unless a coherent deep dive justifies a separate page within its file boundary. Number a substantial execution flow from trigger to outcome and attach file or symbol references to the meaningful transitions. Explain the role of each step and the information passed, rather than paraphrasing every line.

Keep documented intent, source-supported behavior, test expectations, and runtime observations distinct. Note missing evidence next to the affected transition and summarize consequential limits. Keep a saved walkthrough self-contained; use conversation to resolve consequential choices, not to leave its outcome in another chat turn. For follow-up documentation, update the relevant flow in its existing page; for a chat question, explain the selected branch without repeating the whole guide.
