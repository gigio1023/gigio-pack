# Design Principles

Why the pack is shaped this way. Every rule in `skills/` should trace back to
something on this page; a rule that doesn't is a removal candidate.

These principles came out of repeated correction rather than up-front design —
several early assemblies were built, used, and thrown away first. Where a
principle exists because something failed, the failure is stated.

## The problem

Working solo across Claude Code, Codex, and Cursor, with models of very
different strength, on projects that span many sessions:

1. Any device tuned to one harness or one model generation stops paying off.
2. Big work is not one implementation session. It is planning, research,
   experiments, implementation, and review interleaved across sessions.
3. Direction set by detailed spoken instruction is flexible, but the judgment
   and the current state disappear when the session ends.
4. Imposing fine-grained procedure on a strong model damages the thing that
   makes it strong — its ability to find a better route than the one you
   scripted.
5. A weak executor is the opposite: without explicit scope, order, authority,
   verification, and stop conditions, delegation is not safe.
6. The work is not only conventional software. Open-ended problems belong in
   the same picture.
7. Any device that creates homework — documents to maintain, skill names to
   memorize — will not actually get used.
8. It is not enough for each skill to be individually useful. When a skill
   enters, what it leaves behind, and who consumes that next must be visible
   in one connected flow.

In one sentence:

> No heavy workflow pack, but no more structureless spoken instruction either.
> Don't suppress the strong model, keep the weak one usable when needed, and
> stop losing the direction and state of large work.

## Six constraints

Every component must satisfy all six. These are the actual filter — most
rejected ideas died here, not on quality.

| # | Constraint | What it rules out |
| --- | --- | --- |
| C1 | **Harness-agnostic.** Claude Code, Codex, Cursor, and whatever comes next | Anything that binds to one harness's hooks, commands, or session model |
| C2 | **Model-generation tolerant.** A generational jump should require no rework | Procedure that compensates for a *current* model's weakness — its value goes negative as models improve, because it shackles the stronger model |
| C3 | **Fill only what native features don't.** No competing with plan mode, goals, or resume | Re-implementing drive. Native owns pulling work forward; this pack owns what remains afterward |
| C4 | **Explicit invocation plus ambient prose only.** No hooks, runtimes, daemons, or services | Background state machines, watchdogs, anything not readable and hand-editable |
| C5 | **Restatement-replacement test.** A field earns its place only if its absence forces you to re-explain the same thing in chat | Fields that exist because a template had a slot for them |
| C6 | **In-flow only. Zero homework.** | Anything requiring maintenance outside the moment it pays off |

C2 deserves the emphasis. The strongest models follow a badly designed
procedure just as faithfully as a good one, so the opportunity cost of an
unnecessary step grows with every generation. The test:

> If the model gets twice as smart tomorrow, does this text help, stay
> neutral, or get in the way?

If it gets in the way, cut it.

## What ages well

Surveying a couple of dozen agent workflow systems produced a consistent
lifespan ordering:

| Layer | Lifespan | Why |
| --- | --- | --- |
| Runtimes, hooks, orchestrators | Shortest | Commands that presuppose each other are invalidated wholesale when the model or harness changes |
| Prompt procedure (forced step sequences, iron laws) | Short | Removed by their own authors once native triggers arrived |
| **Statements of intent** ("record it when you deviate") | Long | A stronger model follows them better. Nothing to fix |
| **Record formats** (markdown ledgers) | Longest | A decision log is still a decision log in ten years |

Hence: **put intent and format into the durable layer, never compensating
procedure.**

## Contract steps, not cognition steps

Numbered steps belong only where order or completeness is part of
correctness:

- prerequisite retrieval,
- approval boundaries,
- required artifact stages,
- validation,
- an externally auditable pipeline.

Everywhere else, state the outcome, the invariants, and the stop condition,
and let the model choose the route. **If removing a step leaves accuracy,
safety, and auditability intact, remove it.**

The four-station split (setup → plan → execute → review) survives this test
precisely because the station boundaries *are* approval and verification
points — an auditable fixed pipeline is the one shape the rule endorses.

Rules are not judged on whether they are good rules, but on whether their
value rises or falls as models improve. The five justification types a rule
may claim, and the audit procedure for each model generation, live in
[rule-ledger.md](rule-ledger.md).

## Records: separate slow identity from fast state

A project's identity (why, what) changes slowly; its state (how far) changes
fast. Mixed into one file, both rot.

- `PROJECT.md` holds identity, with a human-owned section at the top.
  Decisions recorded there are not re-litigated by later sessions.
- Plan files under `.plans/` are short-lived and disposable.
- Handoff notes are one-shot: consumed, then discarded. Records are
  permanent. Don't mix the two natures.
- Trust only files that get committed. An earlier assembly kept official
  state where it was never committed, and the state evaporated.
- Records are self-reported and therefore biased — review runs in a fresh
  context, never as self-review.

Deviations are recorded in four fields: **what the plan said → what reality
revealed → the conservative choice taken → when to revisit.** That shape is
used everywhere in this repo, including the decision log.

## Plans are written for a reader with no memory

- Stable append-only IDs. Never renumber; everything else references them.
- Per task, separate `files` / `action` / `acceptance` / `verification`.
  Acceptance (what must be true) and verification (how you check) are
  different axes.
- Parallelism comes from the plan file's data structure — stage, prerequisite,
  owned files — not from prompt wording asking for parallelism. Measured:
  instruction alone produced no multi-dispatch.
- Conflict prevention is ownership partitioning at planning time, not locking
  at execution time. Lock machinery observed in the wild was dead code.
- Plan fields are **facts, not instructions**, so the same file survives both
  solo execution and parallel dispatch.
- No implementation code in a plan — signatures only. Code in a plan drifts
  away from the code in the repo.

## One source, two resolutions

The strong-model path is the default: thin instruction, preserved autonomy.
The detailed path — explicit scope, order, authority, verification, stop
conditions, plus domain guidance bundled in — activates only when the user
explicitly chooses a lower-capability executor.

Never classify by model name, price, or speed. That is the user's call, and
the detailed path costs autonomy when applied to a model that didn't need it.

## Verification

- A green command proves only what that command can check. Read the output.
- "It ran and found nothing" is not the same as "it never ran."
- Completion requires three things together: a results entry, a real change,
  and a passing check.
- Never retry with the same model and the same prompt. Cap retries.
- Judgment vocabulary keeps "could not verify" as a distinct value, separate
  from pass and fail.
- Nothing is recorded as done before it has actually been used. An earlier
  assembly was written up as "built" while its real usage count was zero;
  that entry is the reason this rule exists.

## Human-readable markdown only

Every device must be something a person can read and fix by hand. No daemons,
hooks, watchdogs, or runtime state files. Large abstraction stacks were
rejected on this basis even where they were internally coherent.

Mechanical output-formatting rules (line positions, bold bans, parser
leniency) don't belong in skills either — that is a linter's concern.

## Naming

- The name states the purpose and the outcome: `gigio-write-plan` writes a
  plan; `gigio-execute-plan` executes one.
- Pack-internal references are **unconditional**. "If installed" hedging is
  for harness capabilities only — the pack ships as one unit.
- Prefer the vocabulary of real systems (CI, CODEOWNERS, build systems) over
  inventing a term. Banned unless a real system uses it that way: contract,
  slice, vertical slice, gate, ceremony. Say output/results/log instead of
  evidence.
- A name that reads badly in the author's other language is disqualified. One
  otherwise-good candidate was dropped for exactly this.

## The razor

For any proposed field or artifact, ask:

> Without this, would the user have to re-explain the same thing in chat?

If not, cut it. This single question removed more from the design than any
other rule.
