# Engineering skills

This folder contains the English engineering workflow.

The workflow is split into three areas:

- **[planning/](./planning/README.md)** - define the problem, sharpen terminology, and answer design questions
- **[tasks/](./tasks/README.md)** - turn plans into artifacts, slices, implementation work, and resumable context
- **[maintenance/](./maintenance/README.md)** - improve the structure of the codebase itself

If you want the full day-to-day workflow, read [USAGE.md](./USAGE.md).

## Common entry points

| Goal | Start here |
| --- | --- |
| set up repo policy | `/setup-skills` |
| design a feature | `/grill-with-docs` |
| implement a feature | `/grill-with-docs`, then `/implement` |
| break work into slices | `/to-prd`, then `/to-issues` |
| debug a bug | `/diagnosing-bugs` |
| refactor architecture | `/improve-codebase-architecture` |
| resume later | `/handoff` |

## Artifact policy

This workflow assumes:

- temp artifacts by default
- durable docs only when worth keeping
- no GitHub or commit automation

Durable docs usually mean:

- `CONTEXT.md`
- `docs/adr/`
- `docs/slices/<feature-slug>.md` when you explicitly want slices kept
