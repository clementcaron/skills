# Planning skills

Use the planning skills before you start coding, or whenever the shape of the work is still unclear.

Planning is where you:

- sharpen the problem statement
- align on domain vocabulary
- test a design before committing to it
- decide what is worth persisting

## Skills in this folder

| Skill | Use it when... |
| --- | --- |
| `/setup-skills` | you want to configure durable docs, temp-artifact policy, and domain doc layout for a repo |
| `/grill-with-docs` | you want to stress-test a feature or refactor idea while updating domain docs inline |
| `/grilling` | you want the raw questioning engine without the wrapper |
| `/grill-me` | you want a direct user-invoked way to start grilling |
| `/domain-modeling` | the project vocabulary is fuzzy, missing, or changing |
| `/prototype` | a runnable logic or UI experiment will answer the question faster than more talking |

## Typical planning flows

### Starting a feature

1. `/grill-with-docs`
2. `/prototype` if the hard question is experiential
3. `/to-prd` or `/implement`, depending on scope

### Understanding an unfamiliar area

1. `/grill-with-docs`
2. `/domain-modeling` if the terminology is sloppy
3. `/prototype` if behavior is the unclear part

### Preparing a major refactor

1. `/improve-codebase-architecture` from maintenance
2. back into `/grilling`
3. `/domain-modeling` if the refactor changes language or concepts

## Output expectations

Planning should usually produce one of these outcomes:

- a sharper shared understanding
- a prototype verdict
- a PRD
- a set of slices
- a small number of durable domain docs

If the output is only useful for the current session, keep it in temp.
