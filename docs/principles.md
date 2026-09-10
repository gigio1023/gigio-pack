# Design Principles

Why the pack is shaped this way. Every rule in `skills/` should trace back to something on this page; a rule that doesn't is a removal candidate.

These principles came out of repeated correction rather than up-front design — several early assemblies were built, used, and thrown away first. Where a principle exists because something failed, the failure is stated.

## The problem

Working solo across Claude Code, Codex, and Cursor, with models of very different strength, on projects that span many sessions:

1. Any device tuned to one harness or one model generation stops paying off.
2. Big work is not one implementation session. It is planning, research, experiments, implementation, and review interleaved across sessions.
3. Direction set by detailed spoken instruction is flexible, but the judgment and the current state disappear when the session ends.
4. Imposing fine-grained procedure on a strong model damages the thing that makes it strong — its ability to find a better route than the one you scripted.
5. A weak executor is the opposite: without explicit scope, order, authority, verification, and stop conditions, delegation is not safe.
6. The work is not only conventional software. Open-ended problems belong in the same picture.
7. Any device that creates homework — documents to maintain, skill names to memorize — will not actually get used.
8. It is not enough for each skill to be individually useful. When a skill enters, what it leaves behind, and who consumes that next must be visible in one connected flow.

In one sentence:

> No heavy workflow pack, but no more structureless spoken instruction either. Don't suppress the strong model, keep the weak one usable when needed, and stop losing the direction and state of large work.

## Six constraints

Every component must satisfy all six. These are the actual filter — most rejected ideas died here, not on quality.

| # | Constraint | What it rules out |
| --- | --- | --- |
| C1 | **Harness-agnostic.** Claude Code, Codex, Cursor, and whatever comes next | Anything that binds to one harness's hooks, commands, or session model |
| C2 | **Model-generation tolerant.** A generational jump should require no rework | Procedure that compensates for a *current* model's weakness — its value goes negative as models improve, because it shackles the stronger model |
| C3 | **Fill only what native features don't.** No competing with plan mode, goals, or resume | Re-implementing drive. Native owns pulling work forward; this pack owns what remains afterward |
| C4 | **Explicit invocation plus standing terminology use.** Procedural work waits to be asked; both terminology skills apply on every task. No hooks, runtimes, daemons, or services | Background state machines, watchdogs, anything not readable and hand-editable — and situational descriptions on skills whose misfire costs more than a paragraph |
| C5 | **Restatement-replacement test.** A field earns its place only if its absence forces you to re-explain the same thing in chat | Fields that exist because a template had a slot for them |
| C6 | **In-flow only. Zero homework.** | Anything requiring maintenance outside the moment it pays off |

C2 deserves the emphasis. The strongest models follow a badly designed procedure just as faithfully as a good one, so the opportunity cost of an unnecessary step grows with every generation. The test:

> If the model gets twice as smart tomorrow, does this text help, stay neutral, or get in the way?

If it gets in the way, cut it.

## What may open on its own

C4 was written about mechanism — no hooks, no daemons. The descriptions shipped anyway with the other half of the door open. Several read as situations rather than requests ("when sizable work needs a written plan", "when a large task has independent workstreams"), and a situation is something the model can decide it is looking at. In use they fired across conversations that had asked for none of it. The prior-art survey had already listed *broad auto-triggering descriptions* as a disqualifier in other packs; this one had the same defect.

The deciding question is what a misfire costs. Nine procedural skills have explicit request triggers, because opening them uninvited starts a procedure beyond an ordinary answer:

| Explicit request trigger | Work it starts |
| --- | --- |
| `gigio-project-setup` | `PROJECT.md`, plus edits to `AGENTS.md` and `CLAUDE.md` |
| `gigio-write-plan` | a plan file in `.plans/` |
| `gigio-execute-plan` | the work itself, plus a run log |
| `gigio-review-results` | a re-collection pass over diffs, files, and checks |
| `session-handoff` | a handoff prompt file |
| `share-internal-doc` | a standalone document and a sharing pass |
| `orchestrate-subagents` | a fan-out of subagents |
| `small-model-handoff` | a dispatch to a weaker executor |
| `fable5-model-routing` | a switch to another model |

Each of the nine carries the rule in its own description, because the harness reads descriptions one at a time and a rule kept somewhere else would never be in front of it. Their ordinary entry points are: the user names the skill, the user asks for what it does in any language, or another pack skill name-calls it during a run the user already started. Not task size, not an unfamiliar domain, not a missing spec, not a long session, not a plan file sitting on disk.

The terminology pair is a deliberate standing exception requested on 2026-09-10: use both skills on every task, apply the accepted reference, and maintain relevant definitions and expressions when gaps or errors are encountered. A separate wording request is unnecessary. No relevant change means no forced write or new survey. Explicit read-only tasks still restrict writes. Project setup installs the standing instruction; automatic skill selection alone is not a runtime guarantee.

Five skills retain their existing triggers. Four of them —`deep-interview`, `commit-and-push`, `draft-pr`, `git-worktree-setup` — already describe a request rather than a situation, so a harness matching the description *is* the user asking: you get an interview by asking for one, a commit by saying commit, a PR by saying PR, a worktree by asking for isolation.

`find-unknowns` is the separate discovery exception with a situational trigger. It exists to fire before you know to ask, and its worst misfire is a paragraph you skip. Gating it would remove the one case where an unrequested pass is worth more than it costs.

That line is where C3 sits too. Unrequested procedural work competes with the model's judgment about how to answer. The standing terminology policy requests a specific kind of in-task maintenance; it does not authorize unrelated files, branches, or paid runs.

`python-coding-standards` applies within a requested Python implementation, refactor, review, or project setup. It preserves that request's authority: reviewing code does not authorize editing it, and an oversized file does not start a separate refactoring project. The skill carries coding choices into the work already underway rather than opening another station.

## What ages well

Surveying a couple of dozen agent workflow systems produced a consistent lifespan ordering:

| Layer | Lifespan | Why |
| --- | --- | --- |
| Runtimes, hooks, orchestrators | Shortest | Commands that presuppose each other are invalidated wholesale when the model or harness changes |
| Prompt procedure (forced step sequences, iron laws) | Short | Removed by their own authors once native triggers arrived |
| **Statements of intent** ("record it when you deviate") | Long | A stronger model follows them better. Nothing to fix |
| **Record formats** (markdown ledgers) | Longest | A decision log is still a decision log in ten years |

Hence: **put intent and format into the durable layer, never compensating procedure.**

## Contract steps, not cognition steps

Numbered steps belong only where order or completeness is part of correctness:

- prerequisite retrieval,
- approval boundaries,
- required artifact stages,
- validation,
- an externally auditable pipeline.

Everywhere else, state the outcome, the invariants, and the stop condition, and let the model choose the route. **If removing a step leaves accuracy, safety, and auditability intact, remove it.**

The four-station split (setup → plan → execute → review) survives this test precisely because the station boundaries *are* approval and verification points — an auditable fixed pipeline is the one shape the rule endorses.

Check those boundaries against the whole active request. If the user already asked for several stations, complete each artifact and enter the next requested skill without demanding the same grant again. A missing permission blocks the affected action, not independent work whose authority and prerequisites hold.

Rules are not judged on whether they are good rules, but on whether their value rises or falls as models improve. The five justification types a rule may claim, and the audit procedure for each model generation, live in [rule-ledger.md](rule-ledger.md).

## Records: separate slow identity from fast state

A project's identity (why, what) changes slowly; its state (how far) changes fast. Mixed into one file, both rot.

- `PROJECT.md` holds identity, with a human-owned section at the top. Decisions recorded there are not re-litigated by later sessions.
- Plan files under `.plans/` are short-lived and disposable. Where no PROJECT.md exists — a multi-repository workspace, a vault — a plan names the intent documents it answers to under Judged against instead.
- Project terminology records preserve accepted English names, contextual meanings, expression decisions, source provenance, and superseded findings. `curate-terminology` maintains those records; `use-terminology` applies them. Root `terminology.md` carries representative definitions and an index, detailed documents live under `docs/terminology/`, and `docs/terminology/references.md` holds source records only. Entries link to their sources rather than relying on an unconnected bibliography. The pack ships the workflow, not a competing domain glossary.
- Handoff notes are one-shot: consumed, then discarded. Records are permanent. Don't mix the two natures.
- Trust only files that get committed. An earlier assembly kept official state where it was never committed, and the state evaporated.
- Records are self-reported and therefore biased — review runs in a fresh context, never as self-review.

Deviations are recorded in four fields: **what the plan said → what reality revealed → the conservative choice taken → when to revisit.** That shape is used everywhere in this repo, including the decision log.

## Plans are written for a reader with no memory

- Stable append-only IDs. Never renumber; everything else references them.
- Per task, separate `owns` / `action` / `acceptance` / `verification`. Acceptance (what must be true) and verification (how you check) are different axes. Ownership covers paths, a run's output directory, or an external resource by URL or ID; the root holding `.plans/` need not be a Git repository.
- Parallelism comes from the plan file's data structure — stage, prerequisite, owned files — not from prompt wording asking for parallelism. Measured: instruction alone produced no multi-dispatch.
- Conflict prevention is ownership partitioning at planning time, not locking at execution time. Lock machinery observed in the wild was dead code.
- Plan fields are **facts, not instructions**, so the same file survives both solo execution and parallel dispatch.
- No implementation code in a plan — signatures only. Code in a plan drifts away from the code in the repo.
- The top of the plan — goal, exclusions, what it is judged against — is the user's, in the user's words. The planner proposes where the user said nothing and names those lines in the file until the user confirms or edits them; it never paraphrases what the user did say. Review reads that half first and reports work resting on lines the user never confirmed. A rewrite the user does not recognize draws no correction, and the correction is what the top half exists for.
- A plan names what it was planned against — a commit, a snapshot hash, a dataset or document revision, a named model or tool — and execution re-verifies each line before trusting the plan. An absent named input blocks its tasks; a similar input is not a substitute.

## One source, two resolutions

The strong-model path is the default: thin instruction, preserved autonomy. The detailed path — explicit scope, order, authority, verification, stop conditions, plus domain guidance bundled in — activates only when the user explicitly chooses a lower-capability executor.

Never classify by model name, price, or speed. That is the user's call, and the detailed path costs autonomy when applied to a model that didn't need it.

## Verification

- A green command proves only what that command can check. Read the output.
- "It ran and found nothing" is not the same as "it never ran."
- Completion requires three things together: a results entry, a real change, and a passing check.
- Never retry with the same model and the same prompt. Cap retries.
- Judgment vocabulary keeps "could not verify" as a distinct value, separate from pass and fail.
- Nothing is recorded as done before it has actually been used. An earlier assembly was written up as "built" while its real usage count was zero; that entry is the reason this rule exists.

## Human-readable markdown only

Every device must be something a person can read and fix by hand. No daemons, hooks, watchdogs, or runtime state files. Large abstraction stacks were rejected on this basis even where they were internally coherent.

Mechanical output-formatting rules (line positions, bold bans, parser leniency) don't belong in skills either — that is a linter's concern.

## Naming

- The name states the purpose and the outcome: `gigio-write-plan` writes a plan; `gigio-execute-plan` executes one.
- Pack-internal references are **unconditional**. "If installed" hedging is for harness capabilities only — the pack ships as one unit.
- Prefer the vocabulary of real systems (CI, CODEOWNERS, build systems) over inventing a term. Banned unless a real system uses it that way: contract, slice, vertical slice, gate, ceremony. Say output/results/log instead of evidence.
- A name that reads badly in the author's other language is disqualified. One otherwise-good candidate was dropped for exactly this.

## The razor

For any proposed field or artifact, ask:

> Without this, would the user have to re-explain the same thing in chat?

If not, cut it. This single question removed more from the design than any other rule.

## Terminology as durable project decisions

The terminology pair follows the same six constraints: portable Markdown and existing instruction entry points (C1); field meanings and preservation rules without a model-specific procedure (C2); project records rather than another runtime (C3); the user-requested standing terminology policy (C4); definitions, source scope, and editorial decisions that otherwise have to be repeated in chat (C5); and correction during the authorized task instead of a separate upkeep pass (C6).

Keep curation separate from application because their outputs and authority differ. A definition change needs source verification and a durable record; an ordinary lookup needs only the relevant entry. Both apply continuously under the pack's stated policy, while research and edits remain proportional to the material encountered. The authoritative details live in the project and in each skill's colocated references, not in these design documents.

## Python preferences within implementation

The owner explicitly added Python coding standards on 2026-09-10. This is a scope extension beyond the original loop-only pack. It follows C5 by carrying recurring choices about Pydantic-first models, explicit types, stable enum values, module responsibilities, and uv project management, and C6 by applying them during requested work. The objective is organized, understandable code rather than elaborate architecture. Current user instructions take precedence; existing compatibility requirements need an explicit exception or scoped migration.

Code remains authoritative for implementation. Docstrings and nearby comments supply intent and background that code cannot show; policies and explanations spanning several files may belong in `docs/`. Parallel implementation narratives fail C6 when they create an ongoing code/document synchronization task. The detailed decisions live in the skill, not a second copy in the design record.

The core and references are portable Markdown (C1), with no model-specific procedure (C2), replacement runtime (C3), or unsolicited audit (C4). Pydantic-specific modeling stays in the official external skill. The pack's integration reference identifies the upstream revision and gives a retrieval fallback, so reading guidance does not imply installing packages or creating a competing copy.
