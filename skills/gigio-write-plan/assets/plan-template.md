# <task name>

> **To execute:** invoke the `gigio-execute-plan` skill on this file. To revise the plan, invoke `gigio-write-plan`. If neither skill is installed, work through this file top to bottom.

<!-- stage / needs / owns are facts about tasks, not commands.
     Solo run: read top to bottom. Parallel run: the lead groups by stage. -->

<!-- human-owned: Goal, Out of scope, and Judged against are the user's,
     in the user's words. The planner quotes them where the user said them
     and writes plain proposals where the user did not, naming those lines
     in its announcement and in the last line of Judged against until the
     user confirms or edits them. Renegotiate with the user before changing
     this half; the planner owns everything from Planned against down. -->

## Goal
- What becomes true when this is done. When the result informs a decision, name the decision and what each outcome would mean.

## Out of scope
- What we decided not to do, and why.
- Side effects the executor may not cause beyond what is allowed here: writes outside owned paths, network or paid runs, external systems, messages, commits and pushes.

## Judged against
- PROJECT.md when it exists, and which judgment rule or open question this plan serves. Otherwise the intent this plan answers to, by path: AGENTS.md, a design or research document, a brief, a parent plan this run narrows.
- Proposed, not yet confirmed: <the top-half lines the planner wrote without the user's words, by section — "Goal, second line; Out of scope, third line">. The user deletes this line, or edits the lines it names, once they have read them; the review lists work resting on lines still named here.

## Planned against
- The state this plan was written against, one line each, dated <YYYY-MM-DD>: `commit <short SHA>` of <repository>; `snapshot <sha256>` over <files>; <dataset or document> at <revision or date>; <model, tool, or credential> present at <path>.
<!-- First preflight item in gigio-execute-plan: re-verify every line.
     Commit anchor: git diff --stat <SHA>..HEAD -- <owned paths>.
     An anchor that no longer holds blocks the tasks that depend on it;
     a similar model, dataset, or document is not a substitute. -->

## Next action
- The single first action a fresh session can take from this file alone.

## Shared constraints
- Only the lead edits this file and PROJECT.md — workers never write it (it is outside every worker's owned paths). Workers return results in their final message; the lead records them under Results.
- Decisions that deviate from the plan are appended as "### T<n> deviation" — existing lines are never rewritten.
- Abbreviated roots used below (`R=`, `W=`) are defined here as absolute paths. The root holding `.plans/` need not be a Git repository.

## Interfaces            <!-- only when 2+ tasks share a signature/schema -->
- Fix shared types and signatures here before parallel work starts.

## Tasks
### T1. <task name>
- stage: 1               <!-- same stage = can run at the same time -->
- needs: none            <!-- task IDs that must finish first.
                              "related:" for reference only; "found-during:"
                              for tasks discovered mid-run (no ordering) -->
- owns: src/a.ts, src/b.ts
                         <!-- paths; a run's output directory for a
                              run-shaped task (experiment, sweep case, batch);
                              or an external resource by URL or ID (a page,
                              a dataset revision). Same-stage tasks own
                              disjoint sets -->
- avoid: src/legacy-a.ts — deprecated path, v1 clients still pinned
                         <!-- optional; looks related, must not touch, reason required -->
- delegable: yes         <!-- "no" = needs user input; the lead does it inline -->
- acceptance: <what must be true when this is done>
                         <!-- the axis a command may not reach: a stated
                              finding, a judged result, a felt quality -->
- check: pnpm test tests/a
                         <!-- how you verify the acceptance; task-specific only:
                              a command, a measurement, or a named reader's
                              judgment ("the user reads the draft and confirms
                              the three claims"). project-wide done criteria
                              live in PROJECT.md, stated once -->

## Stop conditions
- Stop and report to the user when any of these holds.
- A task's check fails twice after a repair attempt.
- Key assumption <X> turns out false.
- A Planned against line no longer holds and the plan contradicts what is now there.

## Completion judgment (lead)
A task is done when all three hold — not when a worker says so:
1. Its Results entry is filled in
2. Its owned paths or resources show real change — git log for tracked files; for everything else (a generated file, a run's output directory, an external page or dataset revision), the named artifact or resource itself
3. Its check ran on fresh output and its acceptance holds

A check that ran and came back negative — the hypothesis did not hold, the measurement landed under target — satisfies 3 wherever acceptance was written as "we can say which way it came out". What fails 3 is a check that could not run, or an acceptance that is not met. Two consecutive failures on the same task: stop retrying, report to the user.

## Results
### T1 (recorded by the lead from the worker's final message)
- One-line result:
- Commit or artifact:
- Check command output summary:
- Baseline: (were tests passing or failing before edits)

## Run log
<!-- One block per run, appended by the lead. Never rewrite old blocks. -->
### Run 1 — <date/time>
- Scope: stage 1 (T1, T2)
- Outcome: T1 done, T2 blocked (one-line reason)
- Verdict: blocked — stopped at T2; next run starts by re-dispatching T2
