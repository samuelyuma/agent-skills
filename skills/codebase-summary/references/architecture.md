# Architecture Exploration

## Establish the System

Use project definitions and documentation to identify the system's purpose and the part of the repository under discussion. Verify documented responsibilities against implementation. For multiple applications or packages, identify the relevant ones and their connections before expanding further.

Find executable startup paths and what they assemble: registrations, routes, commands, consumers, scheduled work, or other entry mechanisms present in the code. Follow launch scripts into their targets. A familiar filename or dependency name is a lead, not proof of execution.

Libraries, command-line tools, frontend applications, and infrastructure repositories may have no server-style startup. Start from the public surface that exists: exported modules, commands, routes, events, or pipeline definitions. Say which kind of entry point the system has rather than imposing one.

Finish this pass when the explanation can name the relevant starting points and components with inspected evidence, or state precisely which starting point remains unresolved.

## Map Responsibilities and Connections

Follow imports, project references, registrations, interfaces and their bound implementations, callers, and data access to establish the relevant relationships. Inspect the wiring that selects an implementation rather than treating a declaration as a runtime connection.

For each important component, establish:

- What responsibility it performs and where that responsibility is implemented.
- What calls or triggers it and what information it receives.
- Which other components or external systems it uses.
- What state it owns or changes and what result it exposes.

Separate source dependencies from runtime communication. Identify ownership and read/write paths when state crosses component boundaries. Describe an external integration only as far as inspected adapters, configuration schemas, or repository documentation establish it. An external system's internal behavior can remain unknown.

Discover the boundaries that exist in the code. Folder names and architecture labels in documentation do not establish dependency direction, isolation, or design intent. Describe observed relationships first. Attribute documented intent and label architectural interpretations as such.

## Explain the Map

Use the guide structure in `references/documentation.md` or the focused chat order in `SKILL.md`, according to the requested output. Select components that matter to the user's goal; make their relationships understandable before listing supporting files. Group related source files by responsibility rather than making a chapter or page for each file. Link files and symbols where the reader needs evidence or a place to continue exploring.

Explain configuration only when it changes the relevant wiring or behavior, using safe schemas or names. Treat existing tests as evidence of expectations unless execution results are available. Preserve conflicts between documentation and code and state which inspected implementation supports the described behavior.

For a broad documentation request, establish the system map and use the selected representative flows to provide depth within the guide's scope and file boundaries. For a chat-only overview, stop at a useful boundary and offer a concrete next focus when appropriate. For a focused request, stop once the relevant relationships are explained. Name coverage limits, including uninspected applications or unresolved bindings, without presenting them as missing implementations.
