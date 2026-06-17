# Skills

This repository contains my AI-agent skill library for software engineering work.

The core idea is simple:

- **the human stays in charge**
- **the agent helps with planning, execution, and maintenance**
- **repo history and GitHub operations stay manual unless explicitly requested**

These skills are designed for a workflow where the code and architecture stay understandable because the important decisions are kept in a small set of durable documents, while temporary planning artifacts stay out of the repo by default.

## Repository structure

The repository currently exposes the English workflow, grouped by phase:

```text
skills/
  eng/
    planning/
    tasks/
    maintenance/
```

Start here:

- [`skills/eng/README.md`](./skills/eng/README.md)
- [`skills/eng/USAGE.md`](./skills/eng/USAGE.md)

## Workflow

The engineering workflow is split into three buckets:

1. **Planning** - clarify the problem, sharpen the design, align on domain language, and answer uncertain questions with prototypes when needed
2. **Tasks** - turn the plan into PRDs, slices, implementations, debugging loops, and resumable session context
3. **Maintenance** - improve the structure of the codebase itself so future work becomes easier

## Quick start

| If you want to... | Start with |
| --- | --- |
| configure a repo once | `/setup-skills` |
| design a feature | `/grill-with-docs` |
| implement a feature | `/grill-with-docs`, then `/implement` |
| break a feature into slices | `/to-prd`, then `/to-issues` |
| debug a hard bug | `/diagnosing-bugs` |
| refactor architecture | `/improve-codebase-architecture` |
| continue later in a fresh session | `/handoff` |

For the full day-to-day guidance, read [`skills/eng/USAGE.md`](./skills/eng/USAGE.md).

## Use with `npx skills`

This repository is compatible with the [`skills`](https://github.com/vercel-labs/skills) CLI.

Use `add` to install skills. If you run it without `--skill`, the CLI opens the interactive picker so you can choose exactly which skills to install:

```bash
npx skills@latest add clementcaron/skills
npx skills@latest add clementcaron/skills --list
npx skills@latest add clementcaron/skills --skill grill-with-docs
```

Use `use` to run one skill without installing it:

```bash
npx skills@latest use clementcaron/skills --skill grill-with-docs
```

If you want everything, install all skills from the repo:

```bash
npx skills@latest add clementcaron/skills --all
```

## Artifact policy

This repository uses a strict default:

- **temporary artifacts go to the OS temp directory**
- **durable artifacts stay small and intentional**
- **no automated commits**

The durable artifacts are usually limited to:

- `CONTEXT.md`
- `docs/adr/`
- `docs/slices/<feature-slug>.md` when slices need to survive across sessions

This keeps the repo from turning into a tracker or a pile of stale planning documents.

## Which docs should I read?

If you are using the English workflow:

- start with [`skills/eng/README.md`](./skills/eng/README.md)
- then read [`skills/eng/USAGE.md`](./skills/eng/USAGE.md)
- then use the area READMEs as local indexes:
  - [`skills/eng/planning/README.md`](./skills/eng/planning/README.md)
  - [`skills/eng/tasks/README.md`](./skills/eng/tasks/README.md)
  - [`skills/eng/maintenance/README.md`](./skills/eng/maintenance/README.md)

## What these skills are for

These skills are meant to help with work like:

- designing and implementing features
- understanding an unfamiliar codebase
- debugging hard bugs
- improving test seams
- refactoring shallow modules into deeper ones
- keeping multi-session work coherent

They are **not** meant to replace engineering judgment. They are there to structure it.

## Attribution

Based on Matt Pocock's skills, adapted for my usage.
