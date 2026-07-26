---
name: gigio-project-setup
description: >
  Use when installing the gigio-pack system into a project or auditing an existing
  installation: writing PROJECT.md (diagnosis, pillars, non-goals, judgment
  rules, current risk, current position), wiring shared agent instructions
  into AGENTS.md with a CLAUDE.md bridge, or checking an installed PROJECT.md
  for staleness. Trigger when adopting this pack in a repo, or on "set up the
  project intent file", "PROJECT.md 만들어줘/점검해줘". NOT for writing task
  plans (gigio-write-plan), executing them (gigio-execute-plan), reviewing
  finished work (gigio-review-results), or surfacing unknowns before the work
  itself is chosen (find-unknowns).
---

# Gigio Project Setup

Install or audit the durable intent layer of a project: `PROJECT.md` plus the
instruction wiring that makes every later session actually read it.

## Step 1 — Inspect before asking

Read what exists: PROJECT.md (audit path, Step 4), README, docs, git log,
AGENTS.md and CLAUDE.md. Never ask the user for a fact the repository already
answers. If an equivalent intent document exists under another name, do not
create a rival: ask migrate / keep / rewrite — "keep" means change nothing.

## Step 2 — PROJECT.md: six questions, two speeds

Interview for the gaps only, one question at a time.

**Top half — human-owned.** Mark the boundary in the file (for example
`<!-- human-owned: renegotiate with the user before editing -->`). Model
inference is not a decision until the user confirms it.

1. **Why this exists** — a diagnosis, not an aspiration: one concrete
   incident showing why the current state fails.
2. **Pillars** — 3–5 sentences carrying the intended experience or goal,
   each paired with "this does not mean X".
3. **Non-goals** — reasonable options deliberately excluded, with reasons;
   deferred items carry a re-evaluation condition.
4. **Judgment rules** — numbered, falsifiable imperatives ("when A conflicts
   with B, choose A"), each anchored to the real decision or incident that
   created it.

**Bottom half — model-updated digest, not an archive.**

5. **The most important question right now** — phrased as a risk: what, if
   wrong, sinks everything, and a reasonable way to attack it.
6. **Current position** — ordered by confidence (now / next / under review),
   stated as problems rather than features, plus one line: "what I currently
   measure success by".

Also in the bottom half:

- **Decisions** — settled calls every executor must read before working.
  Supersede rather than delete; record whether each came from user
  confirmation, model inference, or an adopted default. Settled decisions are
  never silently relitigated.
- **Project-wide done criteria** — test/lint expectations stated once here,
  so plans do not repeat them per task.

Writing rules: complete sentences; only vocabulary practitioners of the
domain actually use; explaining a reference never silently turns it into a
requirement.

## Step 3 — Wire the instructions

Edit existing files; do not invent new ones (if neither exists, ask which to
create). Keep the block between marker comments so later updates are
idempotent. Two touch points:

- `AGENTS.md`: a short block stating that PROJECT.md exists and must be
  consulted for significant judgments and completion claims; top-half edits
  need user approval; plans live in `.plans/` (gitignored); routing — to plan
  sizable work invoke `gigio-write-plan`, to execute or resume a plan invoke
  `gigio-execute-plan`.
- `CLAUDE.md`: a first-line `@AGENTS.md` import (or symlink). This path is
  what gets re-injected after compaction and inherited by subagents; content
  placed elsewhere silently disappears.

## Step 4 — Audit path (existing installation)

- Committed-state: `git status` on PROJECT.md and the wired instruction
  files. The intent layer exists only once committed — uncommitted, it
  evaporates outside this checkout.
- Fossil check: compare "current position" against git log and the files.
- Coverage: any of the six questions unanswered, or answered as aspiration
  instead of diagnosis.
- Grade findings three ways: **blocking** (PROJECT.md missing or uncommitted,
  top half edited without approval) / **degraded** (question coverage missing,
  fossilized bottom half) / **advisory** (waste — report it, never block
  on it).

## Step 5 — Report and stop

Say what was created or changed, and what the user should now edit by hand —
the top half is theirs. Ask to commit the new layer (or commit if already
authorized): until committed it protects nothing. Setup never writes plans. For the first piece of
sizable work, continue with `find-unknowns` (territory unclear) or
`gigio-write-plan` (work already chosen).

## Gotchas

- An aspirational "why" ("make X great") is a non-answer — re-ask for the
  incident that shows the current state failing.
- Do not summarize PROJECT.md into the AGENTS.md block. The block carries
  paths and rules; inlined content goes stale the moment the file is edited.
- Do not skip the CLAUDE.md bridge because AGENTS.md "should be enough" —
  Claude Code does not read AGENTS.md on its own.
