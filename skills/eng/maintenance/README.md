# Maintenance skills

Use the maintenance skills when the codebase itself needs attention, even when no single feature is forcing the issue.

Maintenance is where you:

- find structural friction
- improve seams and interfaces
- deepen shallow modules
- resolve messy repo states safely

## Skills in this folder

| Skill | Use it when... |
| --- | --- |
| `/improve-codebase-architecture` | you want a structured review of architectural friction and deepening opportunities |
| `/codebase-design` | you need the vocabulary for seams, interfaces, depth, leverage, and locality |
| `/resolving-merge-conflicts` | you need to resolve conflicts but want to stop before auto-finishing git history operations |

## Typical maintenance flows

### Refactoring a codebase

1. `/improve-codebase-architecture`
2. pick one candidate
3. `/grilling` and `/domain-modeling` as the shape becomes clear
4. `/implement` and `/tdd`

### Improving testability

1. `/codebase-design`
2. identify the seam and interface shape
3. use `/improve-codebase-architecture` if the problem is larger than one module

### Cleaning up after conflict-heavy work

1. `/resolving-merge-conflicts`
2. fix the files
3. run the checks
4. stop at a clean handoff point and decide manually how to finish git history

## Maintenance cadence

You do not need to wait for a crisis.

Good maintenance moments:

- after a bug exposed a structural weakness
- when a feature felt harder than it should have
- when test seams are consistently poor
- when you have spare time and want to keep the codebase navigable
