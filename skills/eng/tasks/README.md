# Task skills

Use the task skills when the plan is clear enough to turn into concrete execution.

Tasks are where you:

- write PRDs
- split work into slices
- implement one slice at a time
- debug with discipline
- preserve session context for later

## Skills in this folder

| Skill | Use it when... |
| --- | --- |
| `/to-prd` | you want to turn the current conversation into a PRD |
| `/to-issues` | you want to break a plan into vertical slices and write them as markdown |
| `/implement` | you are ready to build a feature, fix, or approved slice |
| `/tdd` | you want a red-green-refactor loop at a good seam |
| `/diagnosing-bugs` | the bug is real but the cause is not yet obvious |
| `/handoff` | you want to continue later in a fresh session without losing context |

## Typical task flows

### Simple feature

1. finish planning
2. `/implement`
3. `/tdd` where the seam is good

### Larger feature

1. `/to-prd`
2. `/to-issues`
3. persist slices to `docs/slices/<feature-slug>.md` only if you want them kept
4. `/implement` one slice at a time
5. `/handoff` between sessions if needed

### Bug fix

1. `/diagnosing-bugs`
2. `/implement`
3. `/tdd` for the regression seam

## Important behavior

- temp artifacts are the default
- `/to-issues` still uses its old name, but it now writes **slice documents**, not tracker issues
- `/implement` does **not** auto-commit
- `/handoff` is the bridge between sessions
