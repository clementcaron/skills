---
name: to-issues
description: Break a plan, spec, or PRD into independently-grabbable vertical slices using tracer-bullet slices.
disable-model-invocation: true
---

# To Issues

Break a plan into independently-grabbable vertical slices.

The repo's artifact policy should have been provided to you — run `/setup-skills` if not.

## Process

### 1. Gather context

Work from whatever is already in the conversation context. If the user passes a path as an argument, read that markdown file. Do not assume a remote tracker.

### 2. Explore the codebase (optional)

If you have not already explored the codebase, do so to understand the current state of the code. Slice titles and descriptions should use the project's domain glossary vocabulary, and respect ADRs in the area you're touching.

Look for opportunities to prefactor the code to make the implementation easier. "Make the change easy, then make the easy change."

### 3. Draft vertical slices

Break the plan into **tracer bullet** slices. Each slice is a thin vertical slice that cuts through ALL integration layers end-to-end, NOT a horizontal slice of one layer.

<vertical-slice-rules>

- Each slice delivers a narrow but COMPLETE path through every layer (schema, API, UI, tests)
- A completed slice is demoable or verifiable on its own
- Any prefactoring should be done first

</vertical-slice-rules>

### 4. Quiz the user

Present the proposed breakdown as a numbered list. For each slice, show:

- **Title**: short descriptive name
- **Blocked by**: which other slices (if any) must complete first
- **User stories covered**: which user stories this addresses (if the source material has them)

Ask the user:

- Does the granularity feel right? (too coarse / too fine)
- Are the dependency relationships correct?
- Should any slices be merged or split further?

Iterate until the user approves the breakdown.

### 5. Write the slice output

For each approved slice, write it into markdown.

- By default, write a temp markdown file in the OS temp directory.
- If the user wants a durable artifact, write a single file at `docs/slices/<feature-slug>.md`.
- Keep all slices for one feature in that one file, with one section per slice, so the repo does not accumulate many tracker-like files.

<slice-template>
## Slice

### Title

Short descriptive name.

### Depends on

- Another slice title, if any

Or "None - can start immediately".

### What to build

A concise description of this vertical slice. Describe the end-to-end behavior, not layer-by-layer implementation.

Avoid specific file paths or code snippets — they go stale fast. Exception: if a prototype produced a snippet that encodes a decision more precisely than prose can (state machine, reducer, schema, type shape), inline it here and note briefly that it came from a prototype. Trim to the decision-rich parts — not a working demo, just the important bits.

### Acceptance criteria

- [ ] Criterion 1
- [ ] Criterion 2
- [ ] Criterion 3

### Notes

Optional: prototype learnings, ADR references, or other durable context.

</slice-template>

If the output is temporary, stop after writing it and tell the user where it lives. If the output is durable, keep everything in one `docs/slices/<feature-slug>.md` file unless the user explicitly wants a different structure.
