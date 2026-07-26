# <task name>

> **To execute:** invoke the `gigio-execute-plan` skill on this file.
> To revise the plan, invoke `gigio-write-plan`.
> If neither skill is installed, work through this file top to bottom.

Planned at: commit `<short SHA>`, <YYYY-MM-DD>
<!-- First preflight item in gigio-execute-plan:
     git diff --stat <SHA>..HEAD -- <owned files>
     If in-scope files changed since planning, compare against current code
     before proceeding. -->

<!-- stage / needs / owns-files are facts about tasks, not commands.
     Solo run: read top to bottom. Parallel run: the lead groups by stage. -->

## Goal
- What becomes true when this is done. One line on which PROJECT.md
  judgment rule this serves.

## Next action
- The single first action a fresh session can take from this file alone.

## Out of scope
- What we decided not to do, and why.

## Shared constraints
- Only the lead edits this file and PROJECT.md — workers never write it (it is
  outside every worker's owned files). Workers return results in their final
  message; the lead records them under Results.
- Decisions that deviate from the plan are appended as "### T<n> deviation" —
  existing lines are never rewritten.

## Interfaces            <!-- only when 2+ tasks share a signature/schema -->
- Fix shared types and signatures here before parallel work starts.

## Tasks
### T1. <task name>
- stage: 1               <!-- same stage = can run at the same time -->
- needs: none            <!-- task IDs that must finish first.
                              "related:" for reference only; "found-during:"
                              for tasks discovered mid-run (no ordering) -->
- owns-files: src/a.ts, src/b.ts
                         <!-- run-shaped task (experiment, sweep case, batch):
                              own the run's output directory instead -->
- avoid-files: src/legacy-a.ts — deprecated path, v1 clients still pinned
                         <!-- optional; looks related, must not touch, reason required -->
- delegable: yes         <!-- "no" = needs user input; the lead does it inline -->
- acceptance: <what must be true when this is done>
                         <!-- the axis a command may not reach: a stated
                              finding, a judged result, a felt quality -->
- check: pnpm test tests/a
                         <!-- how you verify the acceptance; task-specific only.
                              project-wide done criteria live in PROJECT.md,
                              stated once -->

## Stop conditions
- Stop and report to the user when any of these holds.
- A task's check fails twice after a repair attempt.
- Key assumption <X> turns out false.

## Completion judgment (lead)
A task is done when all three hold — not when a worker says so:
1. Its Results entry is filled in
2. Its owned paths show real change — git log for tracked files; for
   gitignored outputs (a run's report, generated data), the named artifact
   itself
3. Its check ran on fresh output and its acceptance holds

A check that ran and came back negative — the hypothesis did not hold, the
measurement landed under target — satisfies 3 wherever acceptance was written
as "we can say which way it came out". What fails 3 is a check that could not
run, or an acceptance that is not met.
Two consecutive failures on the same task: stop retrying, report to the user.

## Results
### T1 (filled by the assigned worker)
- One-line result:
- Commit:
- Check command output summary:
- Baseline: (were tests passing or failing before edits)

## Run log
<!-- One block per run, appended by the lead. Never rewrite old blocks. -->
### Run 1 — <date/time>
- Scope: stage 1 (T1, T2)
- Outcome: T1 done, T2 blocked (one-line reason)
- Verdict: blocked — stopped at T2; next run starts by re-dispatching T2
