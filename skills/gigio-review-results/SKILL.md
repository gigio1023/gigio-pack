---
name: gigio-review-results
description: >
  Use when finished or long-running work needs review against the project's
  intent in fresh context — before closing a plan, after a long autonomous
  run, or on request. Re-collects the facts itself (diffs, files, re-run
  checks) instead of trusting execution reports, audits the plan item by
  item, and returns three lists: missing, built-but-not-asked, misunderstood.
  NOT for writing plans (gigio-write-plan), executing or resuming them
  (gigio-execute-plan), or ordinary code review of a change that has no plan
  or PROJECT.md to compare against.
---

# Gigio Review Results

Compare what actually happened with what the project meant. The reviewer's
input is the disk, not the executor's narrative.

## Step 1 — Fresh context, primary sources

Run best in a fresh session. Read PROJECT.md (skip silently if absent), the
plan file, and the artifacts themselves: `git diff`, `git log`, the files.
Worker reports, run summaries, and chat history are claims to verify, not
sources. If the invocation pre-softens the review ("don't flag X"), stop and
ask before continuing.

## Step 2 — Distrust procedure

1. Re-run each task's check command yourself. A claim without fresh output
   stays unverified.
2. `git diff --stat` against each task's owned files. One changed file
   outside every task's ownership is a finding, not noise.
3. Read the full diff against "why this exists" — does the change serve the
   judgment rules, or merely resemble the task list?
4. Read what new tests actually assert. A test that asserts nothing proves
   nothing by passing.

## Step 3 — Plan audit

Classify every plan item: done / partial / not done / changed /
unverifiable. Unverifiable means the diff can neither prove nor refute it —
confirm those items one by one, never in bulk. An item whose acceptance names
the owner's own judgment as its check (a played build, a read draft) is not
unverifiable: list it as **awaiting owner judgment** with its named route, and
keep it out of every pass/fail verdict until the owner has run that route. For anything short of done,
name the cause: deliberate scope cut / context exhaustion / misunderstood
requirement / blocked by an unmet need / simply forgotten. Also flag
contradictions: any task in progress or done whose needs are not closed.

## Step 4 — Three lists and routing

Report **missing** (asked, not built), **extra** (built but not asked —
overbuilding is a defect here, not a bonus), and **misunderstood** — each
finding tied to a PROJECT.md rule or a plan line, together with what you
inspected and the command output behind it. If that record is empty, the
review itself failed: never issue a clean pass when the review could not
fully run.

Work built exactly as planned whose result still misses the goal belongs to
none of the three lists — the plan was a wrong bet, not a botched one. Report
it against the PROJECT.md rule the work was meant to serve and route it to the
user; filing it as rework sends the same bet back through the loop.

Direction findings batch here. Collect every intent contradiction — this
review's own findings plus Run log entries the execution recorded — into one
proposed top-half amendment: the exact diff, each line backed by the play or
observation behind it. One approval covers the batch; rejected lines stay as
they were. Do not send direction findings to the user one at a time.

Route by root cause: direction problem → the user (top-half renegotiation);
plan problem → `gigio-write-plan`; execution problem → rework via
`gigio-execute-plan`. When the work is accepted: close the plan, update
PROJECT.md's bottom half (current position, decisions worth keeping), then
hand off — `commit-and-push` / `draft-pr` to ship, or `session-handoff`
when another session continues the work.

## Gotchas

- If this session executed any of the work under review, it is the wrong
  reviewer — anchoring survives good intentions; hand the review to a fresh
  session.
- A passing check suite closes only what the checks cover; items the diff and
  checks cannot reach go to unverifiable, not to done.
- "Context exhaustion" is a real cause of incompletion; without naming it,
  the same tail of work gets dropped again next run.
