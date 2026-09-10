---
name: gigio-execute-plan
description: >
  Use only when the user asks to execute or resume a plan file from .plans/ —
  "run the plan", "continue", "이어서 진행해줘", a plan path, a task ID, a
  stage name, or the skill name. Re-verifies what the plan was planned against
  first, dispatches independent same-stage tasks through available workers, judges
  completion from files and fresh check output rather than worker reports, and
  appends a run log. Resuming after an interruption is the same entry point
  invoked again. NOT for writing or revising plans (gigio-write-plan) or
  reviewing finished work against intent (gigio-review-results); when the plan
  itself turns out wrong, stop and route back to gigio-write-plan instead of
  patching it here. Never activate because a plan file exists — the user starts
  the run.
---

# Gigio Execute Plan

Execute what the plan file says — nothing more. Decomposition and ordering already live in the file as data; this skill owns preflight, dispatch, completion judgment, and the run log.

## Step 0 — Scope from the argument's shape

No flags — never infer one is active just because it is documented.

- task ID → that task only
- plan path → the whole plan
- stage name → that stage
- nothing → the next ready task of the most recent plan in `.plans/`

Read PROJECT.md first (skip silently if absent) — its Decisions section and project-wide done criteria bind every run — then whatever else the plan lists under Judged against.

## Step 1 — Preflight

Before trusting the plan, compare it to what is there now:

1. Freshness: re-verify every line under Planned against. A commit anchor: `git diff --stat <SHA>..HEAD -- <owned paths>`. A snapshot hash: recompute it. A dataset or document revision: re-read it. A named model, tool, or credential: check that it is present. If in-scope state changed since planning, read its current state before proceeding; pause the affected task on a material contradiction with the plan. A named input that is absent blocks the tasks that need it — a similar model, dataset, or document is not a substitute, and results obtained with one are not the plan's results.
2. A dirty working tree beyond the plan's scope.
3. Tasks marked done whose owned paths or resources show no changes.
4. Changed owned paths or resources whose Results entry is empty.

For unrelated dirty files, preserve them and continue. For a mismatch in owned paths, resources, or completion records, inspect the diff and existing results first; repair an unambiguous record discrepancy within the requested run and log it. Ask only when the resolution would redo user work, choose new intent, or cross authority. Identify the affected task and continue independent eligible work when the plan's ordering allows it. An unavailable checker remains unverified; continue only where its absence does not hide a prerequisite or ownership risk.

A user-named single task narrows preflight to that task and its prerequisites; it does not waive ownership or current-state checks. The full set applies to whole-plan runs. Resume is not special: the first stage with unfinished tasks is the entry point, so re-invoking this skill is idempotent.

## Step 2 — Select and dispatch

- Eligible: tasks whose needs are all done. Never start a higher stage while a lower stage has unfinished tasks.
- Go parallel when two or more eligible same-stage tasks own disjoint paths or resources and their checks run independently. Fan-out width = the number of disjoint ownership sets, capped by the harness limit (unknown limit → 1). Otherwise run one task and give the reason in one line.
- Workers are the harness's built-in delegation only — subagents or agent teams, never CLI child processes. Check actual tool availability, not the runtime's name; with no delegation available, run the tasks inline, sequentially, under the same rules.
- Submit eligible independent tasks before waiting for their results, using the harness's actual concurrent dispatch mechanism. Single-message dispatch is a dated workaround, not proof of parallel execution on every harness. A dispatch prompt is paths and IDs — plan path + task ID + PROJECT.md path + scalar config values. Do not paraphrase the plan into the prompt: restated content drifts the moment the file changes; workers load their own context from the file.
- Include these worker limits in every dispatch; do not assume inherited skills or session rules enforce them:
  1. Do not spawn subagents.
  2. Do not invoke other skills — especially open-ended research skills.
  3. Write only within your owned paths or resources; if a needed change falls outside them, stop and report instead of editing.
  4. Read anywhere you need.
  5. Do not claim completion without your check command's output.
  6. Never mark a failed task done — report the failure. Add: read PROJECT.md's Decisions before working; if the task conflicts with a settled decision, surface the conflict rather than silently diverging.
- For a weaker executor model, build the dispatch with `small-model-handoff` — its fields may be satisfied by referencing the plan file instead of restating it. Use `git-worktree-setup` when workers need isolated checkouts.

## Step 3 — Judge, route failures, close out

A task is done only when all three hold — a worker saying so is none of them: its Results entry is filled, its owned paths or resources show real change (git log for tracked files; the named artifact or resource itself for everything else — a generated file, a run's output directory, an external page or dataset revision), and its check ran on fresh output ("should work" is not output) with the task's acceptance met. Where acceptance reads "we can state which way it came out", a negative result meets it — the repair path below is for a check that could not run, not for a measurement that came back unwelcome. A deviation documented in Results is judged on content, not blocked reflexively — the prohibition is on undocumented divergence.

Failure routing — never retry the same model with the same prompt; change the dispatch based on what actually failed (add the missing paths, or move to a stronger model — your diagnosis, not a lookup table). A plan defect — wrong decomposition, an oversized task, a false premise — goes back to `gigio-write-plan` or the user, never patched here. Two failures on the same task after a repair attempt: stop retrying, report.

Evidence against the intent itself — play that contradicts a pillar, an observation that reverses the direction — is not a failure and does not stop the run: record it in the Run log and keep executing, unless continuing is certain waste. `gigio-review-results` batches these into one top-half amendment proposal; mid-run direction stops are reserved for certain waste.

Stage end: map actually-modified paths and resources to their authors. Disjoint — costs nothing, move on. Overlap — resolve once and warn the next stage's dispatch.

Close out each task in this order: real changes on disk → Results recorded → status updated. Preflight items 3–4 detect exactly the intermediate states this order forbids.

Guardrails: do not leave a task half-done silently; do not create tracking files outside the plan — the plan file and its run log are the only state.

## Step 4 — Run log and verdict

Append one block to the plan's Run log: time, scope, per-task outcome, and a one-line verdict — advanced / blocked / no work / needs human / could not verify. "Could not verify" is distinct from pass and fail: checks that never ran are not reported as passing. Record "ran, found nothing" explicitly — a missing entry reads as "did not run".

When the run closes the plan, point to the next stations: fresh-context review with `gigio-review-results`, then `commit-and-push` to land the work.

## Gotchas

- If delegation quietly degraded to inline work, the run log must say so — progress framed as parallel workers that never ran is fabrication.
- A worker's mid-task discovery becomes a found-during task for the next plan revision; it is never silently absorbed into this run's scope.
