# Contributing

A personal pack, but it holds itself to the same conventions as
[gigio1023/agent-skills](https://github.com/gigio1023/agent-skills). Rules for
agents working in this repository live in `CLAUDE.md`; this file is the
human-facing summary of the same contract.

## Layout

```
skills/<skill-name>/            one flat directory per skill (13 total)
  SKILL.md                      the skill — frontmatter + body
  references/                   detail the body links to (optional)
  assets/                       templates the skill fills in (optional)
docs/                           design record — NOT skill payload
  principles.md                 constraints every part must satisfy
  rule-ledger.md                why each load-bearing rule exists
  decisions.md                  what was tried and what replaced it
  prior-art.md                  what was surveyed, taken, and left
```

Everything a skill needs stays colocated under its own directory. `docs/` is
rationale and history; nothing in `skills/` may depend on it.

## Skill contract

- Frontmatter is exactly two fields: `name` (must equal the directory name)
  and `description`.
- The description carries a `Use when …` trigger, a `NOT for …` boundary, and
  one line that separates the skill from its nearest sibling
  (`session-handoff` vs `small-model-handoff` is the reference example).
- Bodies are English. Aim for decision rules over step transcripts, roughly
  400–2,500 tokens, with an 80% path up front and detail pushed to
  `references/`.
- **Contract steps, not cognition steps.** Numbered steps only where order or
  completeness is part of correctness: prerequisite retrieval, approval
  boundaries, required artifact stages, validation, auditable pipelines.
  Otherwise state the outcome, invariants, and stop conditions, and let the
  model choose the route. If removing a step keeps accuracy, safety, and
  auditability intact, remove it.
- Sibling references are unconditional. "If installed" hedging is reserved for
  harness capabilities, never for pack skills.
- Names state purpose and outcome (`gigio-write-plan` writes a plan). Renaming
  anything means: directory + frontmatter + every cross-reference + README +
  `CLAUDE.md` + a re-install.
- No evaluation scaffolding, benchmarks, or scoring artifacts inside
  `skills/`. Migrated skills that carry legacy maintenance fixtures keep them
  (preserve-original-strengths rule), but do not add new ones.
- Migrated skills are edited minimally — one to four focused edits per pass.
  Full rewrites are for broken structure only.

## Before finishing any change

1. `npx --yes skills add . --list --full-depth` reports **exactly 13**
   skills.
2. Every relative path referenced from a changed `SKILL.md` exists on disk.
3. Frontmatter `name` still equals the directory name for anything touched.
4. Re-read the changed skill and `README.md` together — packaging claims and
   docs must not drift apart.
5. A load-bearing rule (dispatch, preflight, ownership, verification) may not
   be changed before checking its justification type in
   [docs/rule-ledger.md](docs/rule-ledger.md). Deletions and
   reviewed-and-kept verdicts are recorded there.

## After merging

Re-run the install command in the README. Installs are **copies**, not
symlinks — repository edits are invisible to agents until reinstalled.

## Design record

- Direction changes append an entry to [docs/decisions.md](docs/decisions.md)
  using the same four fields the pack asks of every deviation: what the plan
  said → what reality revealed → the conservative choice taken → when to
  revisit. Keep the reversals; they are the expensive part.
- A new model generation is an audit event
  ([docs/rule-ledger.md](docs/rule-ledger.md#generation-audit)): re-verify
  measured-workaround rules, collect removal candidates.
- A principle belongs in [docs/principles.md](docs/principles.md) only if some
  rule in `skills/` actually traces back to it. A rule that traces to nothing
  is a removal candidate, not a reason to invent a principle.

## Commits and PRs

- Conventional prefixes (`feat:`, `fix:`, `docs:`), one logical change per
  commit, implementation and its checks together.
- Every non-trivial commit carries a structured body with four labeled
  sections, each a short bullet list of concrete facts:
  - `Context:` — the state that made the change necessary: the incident,
    measurement, or user decision behind it, not a restatement of the subject.
  - `Changes:` — what changed, grouped by skill or document, precise enough
    to navigate the diff.
  - `Results:` — what is now true that was not before: behavior, guarantees,
    recorded policy.
  - `Validation:` — the commands run and what they reported, plus what was
    deliberately not run and why. `Not run` with a reason beats silence.
- Small mechanical commits (a typo, a link fix) may drop `Results:`;
  `Context:` and `Validation:` stay.
- Bodies state facts, never process narration. If a bullet would survive with
  "various", "minor", or "improve" as its verb, it is not specific enough.
- PRs are drafts by default and use concise English. The repository template
  wins; without one, use `## Context` and `## Changes`. Add `## Validation`
  only for results CI cannot prove or a material CI caveat, and collapse long
  supporting details (the `draft-pr` skill in this pack is the reference).
