# AI Workflow Rules

## Approach

Use the context files as the source of truth for the current Django state. Before making changes, inspect the relevant source files, make a small implementation, and verify it end to end.

## Recommended Working Pattern

1. Read the context files first.
2. Inspect only the source files needed for the task.
3. Implement one boundary at a time.
4. Run the smallest useful verification command.
5. Update the context files if architecture, scope, or conventions change.

## Scoping Rules

- Work on one feature unit at a time.
- Prefer small, verifiable increments over large speculative changes.
- Do not combine unrelated system boundaries in a single implementation step.
- If a request affects templates, styles, and settings all at once, split it unless the change is tiny and directly coupled.

## When to Split Work

Split a task if it touches:

- routing and styling,
- server configuration and business logic,
- multiple unrelated pages or apps,
- a requirement that is still ambiguous.

If a change cannot be verified quickly with `python manage.py check` or a browser response, the scope is too broad.

## Handling Missing Requirements

- Do not invent product behavior that is not defined in the context files.
- If a requirement is ambiguous, update the relevant context file before implementing.
- If a requirement is missing entirely, add it to [progress-tracker.md](/Users/somesh/ghost-ai.worktrees/js-to-python-django-migration/context/progress-tracker.md) as an open question before continuing.

## Protected Files

- Do not edit third-party or generated library internals.
- Do not reintroduce the deleted Next.js/React scaffold unless explicitly asked.

## Verification and Handoff

Before handing work off to another agent:

1. The implementation works in its defined scope.
2. `python manage.py check` passes.
3. If UI changed, the page was actually opened and inspected.
4. [progress-tracker.md](/Users/somesh/ghost-ai.worktrees/js-to-python-django-migration/context/progress-tracker.md) matches the current state.

## Documentation Sync

Update context files whenever you change:

- architecture,
- storage,
- conventions,
- scope,
- or the developer workflow for this repo.
