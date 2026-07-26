# Prior Art

What was surveyed before writing this pack, what was taken, and what was left.
Kept so that a later change can start from "this was already considered" rather
than from scratch.

Roughly thirty agent workflow systems, skill packs, and planning harnesses were
read at source level across eight research rounds, plus first-party
documentation and measured claims. Nothing was adopted wholesale. Every system
below contributed either a mechanism or a counter-example.

The filter is always the [six constraints](principles.md#six-constraints) — a
rejection here means "does not fit this pack's constraints," not "is a bad
system." Several rejected systems are excellent at what they set out to do.

## What the survey confirmed

These were already the plan and survived contact with the evidence:

- **Three record types** — a slow identity document, short-lived plan files, and
  pointers. One surveyed system had already codified "the plan file is working
  memory, not a deliverable; gitignore it and promote deliberately." Most others
  lean everything durable and suffer committed-artifact bloat as a result.
- **Intent-first review in a separated context.** Measured research supports it:
  tuning file structure did not move instruction-following rates, whereas
  session length and generation volume did. The budget belongs in re-grounding
  and separated review, not in polishing documents.
- **Strong-model autonomy as the default.** The clearest counter-example in the
  survey was a system that structurally forbids going back from execution to
  planning — even when the model has concluded the plan needs rewriting.
- **Markdown-only.** Two systems in real daily operation run on nothing but
  markdown, one mirroring across eight harnesses.
- **Execution as an explicit invocation.** Nine of ten implementations read
  separate it; the one that didn't is a thousand-line outlier.
- **Planning-time ownership partitioning.** Verified by a real incident in one
  project's issue history.
- **A pack of about five to a dozen skills.** One project abandoned its own
  orchestration layer after significant adoption — supporting the rule that the
  execution skill must not redo decomposition and ordering.

## What the survey changed

1. **Pointer wiring.** Claude Code does not read `AGENTS.md`. Planting must be a
   pair: `AGENTS.md` plus a `CLAUDE.md` bridge (first-line import or symlink).
2. **Body placement is the compaction-survival path.** Only paths imported from
   the root `CLAUDE.md` get re-injected from disk after compaction and inherited
   by subagents. Content placed in path-scoped rules or nested files silently
   disappears. Principle: **pointers where they get re-injected, bodies in the
   file that gets re-read.**
3. **Review needs input independence, not just context independence.** One
   system's judge had genuinely fresh context but was fed the executor's own
   self-description, which made it powerless. LLM judgment of completion claims
   measured weak across five judges and five prompts. So the reviewer's job is
   not to judge — it is to (a) collect independent evidence by re-checking files,
   runs, and environment state, and (b) compare item by item against the identity
   document. The second is text comparison, which models do well.
4. **Question wording.** "Why does this exist" is forced to be a **diagnosis** —
   one concrete incident of why the current state doesn't work — rather than an
   aspiration. "The most important open question" is forced to be a **risk** —
   what, if wrong, collapses everything.
5. **Cheap packets pass paths, they don't compile content.** One project deleted
   its eight-section assembled brief in a controlled evaluation and replaced it
   with three path slots, reaching equal quality at a fraction of the prompt
   size. Inlined bytes go stale the moment the file is edited. So the plan file
   is written to be self-sufficient, and the packet carries paths plus execution
   discipline only.

## Mechanisms adopted

| Mechanism | Where it landed |
| --- | --- |
| Stable append-only IDs, never renumbered | Plan template |
| `files` / `action` / `acceptance` / `verification` separated per task | Plan template |
| Requirement ↔ task coverage table, so a missing requirement shows structurally | Plan template |
| Plan-time SHA plus freshness diff | Plan template, execution skill |
| Three prerequisite edge types (blocking / related / derived) | Plan template |
| Forbidden-files list with a mandatory reason | Plan template |
| Append-per-round execution log | Plan template |
| Two verification layers: task acceptance plus project-wide criteria | Plan template, review skill |
| Judgment rules anchored to the actual decision that produced them | `PROJECT.md` structure |
| Human-owned section tag | `PROJECT.md` two-speed structure |
| A decisions section that later sessions may not re-litigate | `PROJECT.md` |
| Fail-open start check | Execution skill |
| Worker prohibition list (no recursive spawning, absolute paths, never mark failure complete) | Worker preamble |
| Loud fallback — a silent fallback is a test failure | Execution skill |
| Deviation recorded twice: central four-field log plus an inline breadcrumb at the change site | Notes convention |
| Just-in-time planning — detail only the next stage | Planning skill |
| Ground-truth evaluation, and the courage to delete a feature that fails it | Repository maintenance |

## Not adopted

| Concept | Reason |
| --- | --- |
| State machines, transition tables, stop-hook session control | Structure refusing the model's judgment is the exact failure this pack is built against. Violates C2 and C4 |
| Multi-stage intent rewriting pipelines | Intent lives in one document. Every rewrite dilutes the original utterance — that dilution *is* the pain being solved |
| Full bootstrap injection at every session start | A permanent cost. A pointer plus re-reading the file achieves the same thing more cheaply |
| Mandatory TDD, forced red→green | Previously rejected; unchanged |
| Persona role-play and ceremony-heavy halts | Violates zero-homework and generation tolerance |
| Hard dependency on a CLI binary | Cross-harness only holds if plain markdown plus skills is enough |
| A canonical artifact registry with a consistency-check suite | Once the state set grows, maintaining consistency becomes its own subsystem. This is why there are only three record types |
| Separate receipt files by default | Review verdicts flow back into the plan file and the identity document instead |
| Automatic ambiguity scores and numeric exit thresholds | Delegating to a number does not replace a strong model's judgment |
| Per-session persona limits and similar weak-model compensations | A strong model can use the same lens twice in different ways. Violates C2 |
| Build-time prompt assembly | Measured amplification of nearly seven times in one system |
| Instructing primitives the model does not have, via prompt | Gossip and consensus protocols described in prose do not become real |
| Undocumented or unwired commands | One surveyed project documented hundreds of lines of commands that did not exist |
| Any number presented without a measurement | — |

## Deferred, worth revisiting

Not adopted now because each adds a device, but the underlying problem is real.
Revisit if real usage produces the corresponding symptom:

- **Three-state memory transitions** (active / stale / hardened) — dropping a
  lesson from context once it graduates into a rule. Revisit if the identity
  document's lower section bloats.
- **Hard section budgets for a notepad.** Same trigger.
- **Verified vs agent-reported markers** as an explicit display convention.
  Revisit if review output starts blurring the two.

## Open tension

**No successful instance of parallel *writing* was found in the entire survey** —
only read-only parallelism, unverified claims, or implementations belonging to
the abstraction-heavy designs this pack rejects. The decision to support parallel
execution stands, but it is the single least evidence-backed decision here, and
the pilots exist largely to measure it.

The counter-argument on record: workers may need context accumulated across
tasks, in which case the plan file is not a sufficient handoff medium. That is
the second thing the pilots measure.

## Ecosystem caution

- Read `SKILL.md` before installing anything. A methodology hides in the breadth
  of an auto-trigger description — a wide description means that pack's
  philosophy seeps into every task.
- Pin a revision. A published security survey found a meaningful share of public
  skills carrying critical issues.
- Popularity is a weak signal. Inspect substance.
- A package-install failure is a human checkpoint, not something to retry
  through.
