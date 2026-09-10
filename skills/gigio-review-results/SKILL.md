---
name: gigio-review-results
description: >
  Use only when the user asks for finished or long-running work to be reviewed
  against the project's intent in fresh context, or names
  gigio-review-results — before closing a plan, after a long autonomous run, or
  on request. Re-collects the facts itself (diffs, files, run outputs, external
  resources, re-run checks) instead of trusting execution reports, compares the
  result against the user's own words at the top of the plan, audits the plan
  item by item, and returns three lists — missing, built-but-not-asked,
  misunderstood — plus the work that rests on lines the user never confirmed.
  NOT for writing plans (gigio-write-plan), executing or resuming them
  (gigio-execute-plan), or ordinary code review of a change that has no plan,
  PROJECT.md, or other intent document to compare against. Never activate
  because a run just finished.
---

# Gigio Review Results

Compare what actually happened with what the user asked for and what the project meant. The reviewer's input is the artifacts — files, run outputs, external resources — not the executor's narrative, and the yardstick is the user's own words at the top of the plan before it is the planner's task list.

## Step 1 — Fresh context, primary sources

Run best in a fresh session. Read the plan's top half first — Goal, Out of scope, Judged against, in the user's words — then PROJECT.md (skip silently if absent) and the other documents the plan lists under Judged against, then the artifacts themselves: `git diff`, `git log`, the files, run output directories, the external pages or dataset revisions a task owns. Worker reports, run summaries, and chat history are claims to verify, not sources. Treat explicit exclusions as review scope and disclose the resulting coverage limit. Ask only when an exclusion makes the requested verdict misleading; continue the remaining review without inventing a clean pass.

## Step 2 — Distrust procedure

1. Re-run each distinct applicable task check on the reviewed state. One fresh result may cover several tasks with the same command and inputs. Inspect side effects first; a review request does not authorize live writes or paid runs. A check that cannot run within authority stays unverified.
2. `git diff --stat` against each task's owned paths; for owned resources outside Git — a run's output directory, an external page, a dataset revision — compare the resource itself to its planned state. One changed path or resource outside every task's ownership is a finding, not noise.
3. Read the whole result against the Goal in the user's words and, where PROJECT.md exists, its "why this exists" — does the result serve what the user asked for and the judgment rules, or merely resemble the task list?
4. Read what new tests actually assert; a test that asserts nothing proves nothing by passing. Read a report's numbers against the run output they summarize and a document's claims against the sources it cites — a summary is the executor's narrative in another form.
5. Check that the inputs the run actually used are the ones named under Planned against — the model, the dataset revision, the document. Results from a substitute input are reported as such, never as the plan's results.

## Step 3 — Plan audit

Classify every plan item: done / partial / not done / changed / unverifiable. Unverifiable means the diff can neither prove nor refute it — identify each missing fact without requiring a separate user turn per item. Group related user questions after inspecting the available sources. An item whose acceptance names the owner's own judgment as its check (a played build, a read draft) is not unverifiable: list it as **awaiting owner judgment** with its named route, and keep it out of every pass/fail verdict until the owner has run that route. For anything short of done, name the cause: deliberate scope cut / context exhaustion / misunderstood requirement / blocked by an unmet need / simply forgotten. Work that traces only to a top-half line the plan still lists as proposed and not yet confirmed is classified **unconfirmed basis**, apart from misunderstood: the executor did what the file said, but the file never carried the user's word for it. Also flag contradictions: any task in progress or done whose needs are not closed, and any Planned against line that stopped holding during the run without a recorded pause or deviation.

## Step 4 — Three lists and routing

Report **missing** (asked, not built), **extra** (built but not asked — overbuilding is a defect here, not a bonus), and **misunderstood** — each finding tied to a PROJECT.md rule or a plan line quoted as written, the user's words where the line is the user's, together with what you inspected and the command output behind it. Add **unconfirmed basis** as a fourth list when it is not empty: each proposed line, the work resting on it, and the one question that would settle it. Put the lists before the record behind them; a review the user cannot read in one sitting draws no answer, and the user's answer is what closes the loop. If the record is empty, the review itself failed: never issue a clean pass when the review could not fully run.

Work built exactly as planned whose result still misses the goal belongs to none of the three lists — the plan was a wrong bet, not a botched one. Report it against the PROJECT.md rule the work was meant to serve and route it to the user; filing it as rework sends the same bet back through the loop.

Direction findings batch here. Collect every intent contradiction — this review's own findings plus Run log entries the execution recorded — into one proposed amendment: the exact diff to PROJECT.md's top half and, where the contradiction is with the plan's own Goal or Out of scope, the proposed edit to those lines, each backed by the play or observation behind it. One approval covers the batch; rejected lines stay as they were. The reviewer proposes and never rewrites the user's lines. Do not send direction findings to the user one at a time.

Route by root cause: direction problem → the user (top-half renegotiation); plan problem → `gigio-write-plan`; execution problem → rework via `gigio-execute-plan`. When the work is accepted, propose closing the plan and updating PROJECT.md's bottom half (current position, decisions worth keeping) — or, where the project keeps its intent in the documents under Judged against instead, the status those documents carry. Apply those edits when closure or updates are part of the request; review alone does not authorize them. Name the next station: `commit-and-push` / `draft-pr` to ship, or `session-handoff` when another session continues the work.

## Gotchas

- If this session executed any of the work under review, it is the wrong reviewer — anchoring survives good intentions; hand the review to a fresh session.
- A passing check suite closes only what the checks cover; items the diff and checks cannot reach go to unverifiable, not to done.
- "Context exhaustion" is a real cause of incompletion; without naming it, the same tail of work gets dropped again next run.
- A result that matches the planner's paraphrase but not the user's quoted line is misunderstood, not done; the quote is the yardstick.
