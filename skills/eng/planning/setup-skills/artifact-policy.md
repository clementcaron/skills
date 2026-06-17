# Artifact policy

Transient planning and coordination artifacts live in the OS temp directory by default.

## Temporary artifacts

- PRDs
- draft slice breakdowns
- handoff documents
- triage notes
- prototype verdict notes

## Durable artifacts

- `CONTEXT.md`
- `docs/adr/*.md`
- `docs/slices/<feature-slug>.md` when the user explicitly asks to keep slices or needs a persistent multi-session handoff

## Default posture

Do not create tracker-style directory trees inside the repo by default.
Prefer one durable slice file per feature over many per-slice files.
