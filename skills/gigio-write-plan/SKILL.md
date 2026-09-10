---
name: gigio-write-plan
description: >
  Use only when the user asks for a plan file or a revision of one, or names
  gigio-write-plan: produces one file in .plans/ whose top half is the user's
  goal and limits in the user's own words and whose staged tasks carry needs,
  owned paths or resources, acceptance, and checks, anchored to PROJECT.md or
  whatever intent document the project has. The plan is data: a solo session
  reads it top to bottom, a lead uses the same file to dispatch parallel
  workers. Writes the plan, announces it, and stops —
  it never implements tasks itself. NOT for executing or resuming a plan (gigio-execute-plan),
  reviewing finished work (gigio-review-results), or discovery while the work
  itself is still unclear (find-unknowns, deep-interview). Never activate
  because work looks sizable; ordinary in-session task tracking is not this
  skill and needs no plan file.
---

# Gigio Write Plan

Turn chosen work into one self-contained plan file that any later session — solo or parallel, this model or another, this harness or another — can execute without this conversation. The file is what the user hands over, so its top half stays in the user's words and the planner fills the rest.

## Step 1 — Anchor to intent

Read PROJECT.md (skip silently if absent). Then name what else this plan answers to and list it under Judged against by path: AGENTS.md, a design or research document, a launch or interview brief, a parent plan this run narrows. State which judgment rule or open question the plan serves. If the goal contradicts a settled entry in PROJECT.md's Decisions section, stop and surface that instead of planning around it. If no intent source exists and the user cannot say what becomes true when the work is done, route to `find-unknowns` or `deep-interview` first — planning is not discovery. The work need not be code: a research run, a document, a personal decision plan against the same file.

## Step 2 — Write the file

Copy `assets/plan-template.md` to `.plans/<topic>.md` under the root the user works from — a repository, a multi-repository workspace, or a vault. Keep the directory out of version control where there is one (for example via `.git/info/exclude`), and define abbreviated roots as absolute paths in Shared constraints. The rules that carry the weight:

- **The top half is the user's.** Goal, Out of scope, and Judged against are written in the user's words — quoted from the conversation where the user said them, never paraphrased into planner vocabulary. Where the user said nothing, write the planner's proposal as a plain sentence and name those lines both in the announcement and in the last line of Judged against ("Proposed, not yet confirmed: …"), so the user can confirm or edit them and a later review can see which lines never got the user's word. Out of scope also carries the side effects the executor may not cause: writes outside owned paths, network or paid runs, external systems, messages, commits and pushes. A plan the user cannot read and correct in one sitting gets no correction; keep the top short.
- **Fields are facts, not commands.** stage / needs / owns describe each task. Solo execution reads top to bottom; a parallel lead groups by stage. The same file must work both ways.
- **Stage is computed now, not at run time.** No needs → stage 1; otherwise max(needs' stages) + 1; if two same-stage tasks share any owned path or resource, push the later one a stage down. Same-stage tasks own disjoint sets — ownership decided at plan time is the conflict prevention that actually works; nothing else is added at run time.
- **needs is blocking.** Use `related:` for reference-only links and `found-during:` for tasks discovered mid-run; neither affects ordering.
- **`owns` names paths, output directories, or external resources.** For work whose unit is a run rather than an edit — an experiment, a sweep case, a batch job — ownership is the run's output directory; same-stage runs need disjoint output paths, configs may differ freely. For work whose unit lives outside the filesystem — a page, a database row, a dataset revision — ownership is the resource named by URL or ID, and it is owned the same way a file is.
- **`avoid` is optional, its reason is not** — paths or resources that look relevant but must not be touched, and why.
- **Interfaces before parallelism.** When two or more tasks reference one signature or schema, settle it in the Interfaces section — or make a stage-1 task whose only output is the interface file.
- **No implementation code in plans.** Signatures and pointers to existing repo patterns are fine. Full function bodies burn tokens three times (planning, review, implementation) and drift the moment the implementer does it differently.
- **Every task self-contained.** Never "like task N" — executors do not read in order.
- **Fill Planned against with what the plan was written against** — a commit, a snapshot hash over the files it reads, a dataset or document revision, a named model or tool present at a path — each dated and re-verifiable. Execution re-verifies every line before trusting the plan; a line that no longer holds blocks the tasks that depend on it.
- **A plan that narrows a broader design or an earlier plan names that file under Judged against** and carries only this run's scope. The design stays where it is; do not copy it into the new file.
- **Write planning sections only.** Results and Run log stay empty at plan time; they are filled during execution.
- **`acceptance` and `check` are different axes.** Acceptance is what must be true; check is how you verify it. In ordinary code work they coincide, which is why they are easy to collapse — everywhere else they come apart. An experiment's acceptance is "we can state whether the hypothesis held", and a negative result meets it. Work judged by feel has an acceptance and no command. A brief that came back from `find-unknowns` marked comprehension-checked carries its acceptance in words: write those words down rather than inventing a command to stand in for them. `check` holds task-specific commands only; project-wide done criteria live once in PROJECT.md.
- `delegable: no` means the task needs user input or lead judgment — the lead handles it inline instead of dispatching it.

## Step 3 — Downstream consumer note

The executor reads nothing outside this file plus the documents under Judged against. Anything agreed only in conversation and not written into the plan will not be executed. Fields the executor consumes: stage, needs, owns, avoid, delegable, acceptance, check, Judged against, Planned against, Stop conditions, Completion judgment, Results, Run log. The header's "To execute" line is the activation path after this session is gone — keep it intact.

## Step 4 — Announce and stop

Report the saved path, list the top-half lines that are the planner's proposals rather than the user's words — the same lines the file names under Judged against — so the user can confirm or edit them before handing the file on, and name `gigio-execute-plan` as the execution entry. Planning alone ends here. If the user already requested both planning and execution, finish the plan first, then enter that execution skill under the existing grant. Do not require the user to repeat the second half of the request. When a finished plan holds lessons worth keeping, promote them deliberately to PROJECT.md's bottom half; the plan file itself is disposable.

## Gotchas

- Never leave two same-stage tasks sharing an owned path or resource because they "probably won't conflict" — recompute the stages instead.
- Do not rewrite the user's words in the top half into planner vocabulary. A paraphrase the user does not recognize as their own gets no correction, and the correction is the point of the top half.
- A task whose acceptance you cannot state is not plannable yet; that is discovery (`find-unknowns` / `deep-interview`), not a planning problem. A stated acceptance with no command behind it is not that case — say how it will be judged and by whom.
- Do not densify the plan with content executors can load themselves — the plan carries paths, IDs, and facts, not tutorials.
