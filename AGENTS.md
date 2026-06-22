# AGENTS.md

## Behavioral Rules

These rules apply to every coding task. Skills own detailed workflow behavior; the rules below define repo-wide constraints and defaults.

### Rule 1 — Simplicity First
Solve the requested problem with the minimum code that works.
Do not add speculative features, abstractions, or cleanup outside the request.

### Rule 2 — Surgical Changes
Touch only what you must.
Keep changes local, match existing style and conventions, and do not refactor unrelated code.

### Rule 3 — Read Before You Write
Before changing behavior, read the nearby code, immediate callers, shared utilities, and relevant durable docs.
If the current structure is unclear, stop and surface the uncertainty before changing it.

### Rule 4 — Use TDD When the Seam Is Clear
Default to TDD for behavior changes when the expected outcome can be expressed through an existing or natural public seam.
Skip TDD for trivial mechanical edits, but never weaken or rewrite tests just to force a green result.
Tests should verify intent through meaningful behavior, not implementation details.

### Rule 5 — Goal-Driven Execution
Define explicit success criteria, then iterate until they are verified.
Work independently, but stop and surface the blocker if progress stalls.
Do not exceed 5 implementation or debugging iterations without surfacing the issue.

### Rule 6 — Do Not Commit Automatically
Leave commits and history management to the user unless explicitly asked.

### Rule 7 — Surface Uncertainty and Conflicts Explicitly
If code, docs, or patterns conflict, pick the best-supported path, explain why, and flag the conflict.
Do not average contradictory patterns or claim completion when validation, scope, or behavior is uncertain.

### Rule 8 — Match the Codebase
Conformance to the repository's existing conventions beats personal preference.
If a convention seems harmful, surface it explicitly instead of silently introducing a competing pattern.

## Repository Context Template

>Fill these sections for each repository that uses this file.
Use explicit values like `unknown`, `none`, or `not applicable` instead of leaving blanks. Once done, delete this line. 

### Project Context
- Project purpose: `<what this repo exists to do>`
- Primary domain / users: `<who this is for and what problem it solves>`
- Repo shape: `<single app | monorepo | library | service | other>`
- Main apps / services / packages: `<top-level areas the agent should know first>`
- Important durable docs: `<CONTEXT.md | docs/adr/ | docs/slices/ | other | none | unknown>`

### Tech Stack & Architecture
- Primary languages: `<typescript | python | go | rust | etc.>`
- Runtime / platform: `<node | browser | mobile | backend | cli | etc.>`
- Frameworks / major libraries: `<react | nextjs | fastapi | express | etc.>`
- Package manager / build tools: `<pnpm | npm | yarn | bun | make | cargo | etc.>`
- Storage / infrastructure: `<postgres | sqlite | redis | s3 | docker | none | unknown>`
- Key architectural boundaries: `<frontend/backend, api/domain/db, packages, services, etc.>`

### Validation & Commands
- Install: `<command | none | not applicable | unknown>`
- Dev: `<command | none | not applicable | unknown>`
- Build: `<command | none | not applicable | unknown>`
- Test: `<command | none | not applicable | unknown>`
- Lint: `<command | none | not applicable | unknown>`
- Typecheck: `<command | none | not applicable | unknown>`
- Other important commands: `<anything the agent should run or avoid>`

## Security

Never hardcode secrets or sensitive information in code or config files.
Use environment variables or the repository's secure configuration path.
Never commit secrets to version control, including example, backup, or temporary files.
