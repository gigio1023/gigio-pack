# Successor Agent Prompt

## Operating Contract

You are taking over an in-progress task. Continue from the verified state below without redoing completed work. Inspect the named evidence before changing anything, keep the stated scope and authority boundaries, and verify outcomes before reporting them. Treat labeled inferences and unknowns as items to check, not as facts.

Proceed within the recorded grants, preserving their targets and conditions. Ask only for a missing authorization or material user-only decision; continue independent work while it is pending. If a file causes a pause, name the file, clause, and affected action rather than attributing your interpretation to the user. If you cannot continue, report the exact blocker and smallest next action.

## Objective

<State the user-visible outcome in one or two sentences.>

### Next Useful Decision or Result

- <Observable completion condition>
- <Required validation or evidence>
- <Required delivery or publication state>

## Intent and Background

<Explain why this work exists, who or what it serves, and the context needed to make good decisions. Omit session history that does not change the work.>

## Scope and Authority

### In Scope

- <Allowed work>

### Out of Scope

- <Excluded work>

### Existing Grants

- <Authorized action, exact target, conditions, and source of the grant>

### Still Require Confirmation

- <Action whose needed authorization has not been granted>

## Current State

- Status: <not started | in progress | blocked | ready for verification | complete>
- Workspace or project: `<path or identifier>`
- Relevant repositories, data, documents, and live resources: <locations and identifiers; include branches or revisions only when relevant>
- Worktree or artifact state: <clean, changed paths, generated outputs, or other state>
- Last verified at: <timestamp or current-run marker>
- Pending work: <tool or worker handle, last observed state, and how to inspect it before retrying; omit if none>

## Current Understanding

<What the evidence currently supports; meaningful negative or inconclusive findings; competing explanations; prior assumptions or approaches that are no longer current. Link existing records rather than copying them.>

## Decisions and Rationale

| Decision | Why it was made | Evidence or source | Revisit when |
| --- | --- | --- | --- |
| <Decision> | <Concise rationale> | `<path, command, source, or user instruction>` | <Condition or never> |

## Completed Work and Evidence

| Work item | Result | Evidence | Confidence |
| --- | --- | --- | --- |
| <Completed item> | <Observable outcome> | `<observation, dataset review, result record, source, artifact, or check>` | verified |

## Artifact Map

| Path or identifier | Purpose | Current state |
| --- | --- | --- |
| `<artifact>` | <Why the successor needs it> | <verified, inferred, or unknown detail> |

## Current Work Boundary

<The next decision and the bounded work that can inform it. Quick checks within the same question and grants can proceed; direction changes or new long activity require the stated confirmation. A negative or inconclusive finding may be the result.>

## Remaining Work

1. <Highest-priority action, including dependency and expected result.>
2. <Next action.>
3. <Conditional follow-up, only if already useful to specify; do not invent the full project sequence.>

## Blockers, Unknowns, and Risks

- Blocker: <What prevents progress and what resolves it.>
- Unknown: <Missing fact and how to verify it.>
- Risk: <Failure mode, impact, and mitigation.>

## First Actions

1. Read `<specific file or artifact>` and inspect `<specific state>`.
2. Run `<exact safe command or tool action>` to confirm the starting state.
3. Continue with `<first implementation or analysis step>`.

## Verification and Completion Bar

- Run: `<targeted check>`
- Inspect: `<artifact, UI, diff, logs, or external state>`
- Completion evidence: <What must exist or pass before claiming done>
- If a check cannot run: <Required disclosure and next-best evidence>

## Final Delivery

Lead with the outcome. Include the evidence needed to trust it, any material caveat, and the next user action if one remains. Do not claim completion from a plan, an unverified file, or a prior agent's statement.
