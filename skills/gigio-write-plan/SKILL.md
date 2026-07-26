---
name: gigio-write-plan
description: >
  Use when sizable work needs a written plan, or an existing plan file needs
  revision: produces one file in .plans/ with staged tasks — needs, owned
  files, acceptance, checks — anchored to PROJECT.md judgment rules. The plan
  is data: a solo session reads it top to bottom, a lead uses the same file to
  dispatch parallel workers. Writes the plan, announces it, and stops — it
  never executes. NOT for executing or resuming a plan (gigio-execute-plan),
  reviewing finished work (gigio-review-results), or discovery while the work
  itself is still unclear (find-unknowns, deep-interview).
---

# Gigio Write Plan

Turn chosen work into one self-contained plan file that any later session —
solo or parallel, this model or another — can execute without this
conversation.

## Step 1 — Anchor to intent

Read PROJECT.md (skip silently if absent). State which judgment rule or
current question the plan serves. If the goal contradicts a settled entry in
its Decisions section, stop and surface that instead of planning around it.
If unknowns dominate, route to `find-unknowns` or `deep-interview` first —
planning is not discovery.

## Step 2 — Write the file

Copy `assets/plan-template.md` to `.plans/<topic>.md` and keep the directory
out of version control (for example via `.git/info/exclude`). The rules that
carry the weight:

- **Fields are facts, not commands.** stage / needs / owns-files describe
  each task. Solo execution reads top to bottom; a parallel lead groups by
  stage. The same file must work both ways.
- **Stage is computed now, not at run time.** No needs → stage 1; otherwise
  max(needs' stages) + 1; if two same-stage tasks share any owned file, push
  the later one a stage down. Same-stage tasks own disjoint files — file
  ownership decided at plan time is the conflict prevention that actually
  works; nothing else is added at run time.
- **needs is blocking.** Use `related:` for reference-only links and
  `found-during:` for tasks discovered mid-run; neither affects ordering.
- **Runs are tasks too.** For work whose unit is a run rather than an edit —
  an experiment, a sweep case, a batch job — ownership is the run's output
  directory. Same-stage runs need disjoint output paths; configs may differ
  freely.
- **avoid-files is optional, its reason is not** — files that look relevant
  but must not be touched, and why.
- **Interfaces before parallelism.** When two or more tasks reference one
  signature or schema, settle it in the Interfaces section — or make a
  stage-1 task whose only output is the interface file.
- **No implementation code in plans.** Signatures and pointers to existing
  repo patterns are fine. Full function bodies burn tokens three times
  (planning, review, implementation) and drift the moment the implementer
  does it differently.
- **Every task self-contained.** Never "like task N" — executors do not read
  in order.
- **Record `Planned at: <commit SHA>, <date>`.** Execution's freshness check
  diffs the owned files against it.
- **Write planning sections only.** Results and Run log stay empty at plan
  time; they are filled during execution.
- **`acceptance` and `check` are different axes.** Acceptance is what must be
  true; check is how you verify it. In ordinary code work they coincide, which
  is why they are easy to collapse — everywhere else they come apart. An
  experiment's acceptance is "we can state whether the hypothesis held", and a
  negative result meets it. Work judged by feel has an acceptance and no
  command. A brief that came back from `find-unknowns` marked
  comprehension-checked carries its acceptance in words: write those words
  down rather than inventing a command to stand in for them. `check` holds
  task-specific commands only; project-wide done criteria live once in
  PROJECT.md.
- `delegable: no` means the task needs user input or lead judgment — the
  lead handles it inline instead of dispatching it.

## Step 3 — Downstream consumer note

The executor reads nothing outside this file plus PROJECT.md. Anything agreed
only in conversation and not written into the plan will not be executed.
Fields the executor consumes: stage, needs, owns-files, avoid-files,
delegable, acceptance, check, Planned at, Stop conditions, Completion
judgment, Results, Run log. The header's "To execute" line is the activation
path after this session is gone — keep it intact.

## Step 4 — Announce and stop

Report the saved path and say: invoke `gigio-execute-plan` on it. Do not
start executing — not even "just the first task": planning asks and stops,
execution must not stop, and one run holding both stances averages them.
When a finished plan holds
lessons worth keeping, promote them deliberately to PROJECT.md's bottom half;
the plan file itself is disposable.

## Gotchas

- Never leave two same-stage tasks sharing a file because they "probably
  won't conflict" — recompute the stages instead.
- A task whose acceptance you cannot state is not plannable yet; that is
  discovery (`find-unknowns` / `deep-interview`), not a planning problem. A
  stated acceptance with no command behind it is not that case — say how it
  will be judged and by whom.
- Do not densify the plan with content executors can load themselves — the
  plan carries paths, IDs, and facts, not tutorials.
