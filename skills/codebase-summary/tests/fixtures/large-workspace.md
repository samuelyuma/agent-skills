# Large Workspace Evidence

All names, counts, paths, and inventory below are invented for isolated evaluation. Combine this snapshot with `queued-work.md` as the available evidence. The inventory establishes the stated workspace scope only; it supplies no unseen implementation.

## Workspace Inventory

The supplied inventory reports 4,800 source files across the report service, billing application, audit application, and shared packages. The report service's supplied startup, submission, and background implementations are the ones in `queued-work.md`. Runtime connections between those applications are not supplied.

The report service groups its sources under entry points, job submission, report generation, persistence, and delivery adapters. Shared packages contain common model declarations. Generated schemas and vendored dependencies are present. Their names and counts do not establish runtime behavior or require individual documentation pages.

Only the report service is selected for detailed coverage in this evaluation. Its submission and background continuation form the representative end-to-end flow. Billing, audit, shared-package internals, generated sources, and vendored dependencies are outside the detailed coverage. Existing documentation has no maintained codebase guide and establishes no placement convention.

## Additional Evidence for a Follow-Up

The supplied implementations show the worker calling the mailer before changing the job status and removing the pending item. No transaction, exclusive claim, retry policy, or mailer idempotency contract is supplied for those operations. A crash after the mailer call could leave a pending item; any subsequent processing and duplicate effect remain conditional on unknown behavior. No execution results are supplied.
