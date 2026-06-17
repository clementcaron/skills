# Using the engineering skills

This folder contains the English engineering workflow. The skills are grouped into three buckets:

1. **Planning** - clarify the problem, sharpen the design, and decide what is worth keeping.
2. **Tasks** - turn the plan into artifacts, slices, implementation work, and resumable context.
3. **Maintenance** - improve the codebase itself so future work gets easier.

## Quick start

| If you want to... | Start with | Then use |
| --- | --- | --- |
| implement a small feature | `/grill-with-docs` | `/implement`, `/tdd` |
| implement a larger feature | `/grill-with-docs` | `/prototype` if needed, then `/to-prd`, `/to-issues`, `/implement` |
| understand an unfamiliar area | `/grill-with-docs` | `/domain-modeling`, `/prototype` if the behavior is unclear |
| fix a bug | `/diagnosing-bugs` | `/implement`, then `/improve-codebase-architecture` if the bug exposed structural problems |
| refactor a codebase | `/improve-codebase-architecture` | `/grilling`, `/domain-modeling`, `/implement`, `/tdd` |
| resume work later | `/handoff` | reopen the next session with the handoff plus any durable slice or ADR docs |
| set up a repo once | `/setup-skills` | then use the other skills normally |

## Typical workflows

## 1. Implementing a feature

### Small feature

Use this when the feature is clear enough that you do not need formal artifacts.

1. Run `/grill-with-docs` to tighten the requirement and align vocabulary with `CONTEXT.md`.
2. If a logic or UI question needs to be felt rather than discussed, detour to `/prototype`.
3. Run `/implement`.
4. Let `/implement` lean on `/tdd` where the seam is clear.

### Larger or multi-session feature

Use this when the work needs durable planning or should be broken into slices.

1. Run `/grill-with-docs`.
2. If needed, use `/prototype` to answer the hard design question.
3. Run `/to-prd` to write a PRD.
4. Run `/to-issues` to break the plan into vertical slices. Despite the name, this skill now writes slice artifacts, not tracker issues.
5. If the slices need to survive, keep them in one file at `docs/slices/<feature-slug>.md`.
6. Run `/implement` on one approved slice at a time.
7. Use `/handoff` when you need to continue in a fresh session.

## 2. Understanding a codebase

There is no single "understand everything" skill. Instead, pick the understanding shape you need:

- **Understand the domain and naming** -> `/grill-with-docs` and `/domain-modeling`
- **Understand how the system behaves** -> `/prototype`
- **Understand why the architecture feels hard to work in** -> `/improve-codebase-architecture`
- **Understand a failing path** -> `/diagnosing-bugs`

In practice, codebase understanding often looks like this:

1. Start with `/grill-with-docs` and explain what you are trying to learn.
2. Let the skill force precise language and surface contradictions with the code.
3. If the uncertainty is dynamic, not conceptual, use `/prototype`.
4. If the uncertainty is architectural, use `/improve-codebase-architecture`.

## 3. Refactoring a codebase

Use the maintenance skills when you want to improve the shape of the code, not just ship one feature.

1. Run `/improve-codebase-architecture` to surface candidates.
2. Use `/codebase-design` as the vocabulary for evaluating seams, interfaces, leverage, and locality.
3. Once you pick a candidate, use `/grilling` to walk the decision tree.
4. Use `/domain-modeling` if the refactor changes the project vocabulary or reveals a missing term.
5. Implement the chosen change with `/implement`, backed by `/tdd`.

This is the best path when you want to:

- reduce coupling
- make code more testable
- create better seams
- turn shallow modules into deep ones
- make future AI or human work easier

## 4. Fixing a bug

Use `/diagnosing-bugs` first when the bug is genuinely unclear.

1. Build a tight feedback loop.
2. Reproduce and minimize the bug.
3. Generate hypotheses before testing them.
4. Fix the bug with a regression test where the seam is good enough.
5. If the bug exposed structural problems, follow up with `/improve-codebase-architecture`.

If the bug is already obvious and you already have the right seam in mind, you can go directly to `/implement` and `/tdd`.

## 5. Working across sessions

Use `/handoff` when you want a fresh session but do not want to lose the current thread.

Good times to use it:

- after planning, before implementation
- after a prototype, before returning to the main thread
- between slices of a larger feature
- before you stop for the day

Keep the handoff in temp by default. Only persist a slice document or ADR when it is genuinely worth keeping.

## Skill map

## Planning

- `/setup-skills` - configure durable docs, temp-artifact policy, and domain doc layout
- `/grill-with-docs` - sharpen a plan or design while updating domain docs inline
- `/grilling` - raw questioning engine for stress-testing a plan
- `/grill-me` - user-invoked wrapper over `/grilling`
- `/domain-modeling` - actively maintain `CONTEXT.md` and ADRs as decisions land
- `/prototype` - answer a design question with throwaway logic or UI code

## Tasks

- `/to-prd` - turn the current conversation into a PRD
- `/to-issues` - break a plan into vertical slices and write them as markdown
- `/implement` - implement one slice, PRD, or approved chunk of work
- `/tdd` - test-driven implementation loop
- `/diagnosing-bugs` - disciplined debugging loop
- `/handoff` - package the current conversation for a later session

## Maintenance

- `/improve-codebase-architecture` - scan for architectural friction and propose refactors
- `/codebase-design` - vocabulary and principles for deep modules and good seams
- `/resolving-merge-conflicts` - resolve conflicts, then stop at a clean handoff point instead of auto-finishing git history operations

## Which skill should I start with?

When in doubt:

- **new feature** -> `/grill-with-docs`
- **bug** -> `/diagnosing-bugs`
- **refactor** -> `/improve-codebase-architecture`
- **continue later** -> `/handoff`
- **set repo policy** -> `/setup-skills`

If the question is still fuzzy after that, stay in **Planning** longer. These skills work best when the plan is sharp before the execution phase starts.
