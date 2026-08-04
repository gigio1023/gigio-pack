# Rule Ledger

Every load-bearing rule in this pack is registered here with the reason it is
allowed to exist. Before changing a dispatch, preflight, ownership, or
verification rule, look it up here first.

The premise, from [principles.md](principles.md): a strong model follows a
badly designed procedure just as faithfully as a good one. So a rule is not
judged on whether it is a good rule, but on **whether its value rises or falls
as models improve.**

Deciding line: **if removing the step leaves accuracy, safety, and
auditability intact, remove it.**

## The five justification types

| Type | Definition | As models improve | Maintenance |
| --- | --- | --- | --- |
| Storage | Beats context volatility with a file | Holds — memory is not an intelligence problem | Keep |
| Approval boundary | User sovereignty; who owns a decision | **Rises** | Keep |
| Verification | Distrust of executor self-report (incentive problem) | Holds — a stronger executor produces more plausible false claims | Keep |
| Concurrency | Prevents parallel-write conflicts | Holds — concurrency is not an intelligence problem | Keep |
| Measured workaround | Works around a specific harness or model habit | **Expires** | Record the measurement date; re-verify every generation |

There is a sixth type — **cognitive map**, meaning any rule that prescribes a
thinking path. It is deleted on sight and never entered in the ledger. The
lead diagnoses better on its own than a fixed diagnostic table does.

## The ledger

| Rule | Where | Type | Basis | On generation change |
| --- | --- | --- | --- | --- |
| `PROJECT.md` two speeds (human-owned top) + six questions | gigio-project-setup | Storage + boundary | Identity/state separation | Keep |
| Recorded decisions are not re-litigated | gigio-project-setup | Boundary | ADR practice | Keep |
| Plan fields are data, not instructions; three stage-calculation rules | gigio-write-plan | Concurrency + storage | Survives solo and parallel execution alike | Keep |
| No file overlap within a stage (ownership split at planning time) | gigio-write-plan | Concurrency | Demonstrated in surveyed systems; locking alternatives were dead code | Keep |
| Write and stop — planning never executes | gigio-write-plan | Boundary | The two postures are incompatible; merged, they average out | Keep |
| No implementation code, signatures only | gigio-write-plan | Storage (drift) | Plan code drifts from repo code | Keep |
| Plan-time SHA + freshness diff | plan template, gigio-execute-plan | Verification | Downstream tasks almost always reference completed work | Keep |
| Preflight three checks, fail-open | gigio-execute-plan | Verification | A blocking start check strands resumable work | Keep |
| Explicit single-task invocation shrinks preflight | gigio-execute-plan | Boundary (naming it = approving it) | — | Keep |
| Completion requires all three: results entry, real change at the owned paths, check run with acceptance met | gigio-execute-plan, plan template | Verification | Convergent across surveyed systems; refined 2026-07-26 (acceptance axis, untracked outputs) | Keep |
| Never retry same model + same prompt; cap at two | gigio-execute-plan | Verification / stop | Convergent across surveyed systems | Keep |
| Pass the path, never restate the content | gigio-execute-plan, small-model-handoff, orchestrate-subagents | Storage (drift) | Restatement dilutes the original | Keep |
| Worker preamble, six lines of removed authority | gigio-execute-plan | Boundary + **structural premise** | Premise: workers inherit neither skills nor rules | Revisit if a harness introduces worker inheritance |
| Workers use built-in delegation only, no CLI subprocesses | gigio-execute-plan | Structural premise | A dispatch that isn't real makes progress reports fiction | Revisit on harness capability change |
| **Single-message dispatch** | gigio-execute-plan, orchestrate-subagents | **Measured workaround** | Measured 2026-07-25: instruction alone produced no multi-dispatch | **Re-verify per generation and per harness; delete when invalidated** |
| Natural fan-out ceiling (number of non-overlapping ownership sets) | gigio-execute-plan | Concurrency | No magic number | Keep |
| Five judgment values, with "could not verify" distinct | gigio-execute-plan, plan template | Verification | Convergent across surveyed systems | Keep |
| "Ran and found zero" ≠ "did not run" | gigio-execute-plan, gigio-review-results | Verification | — | Keep |
| Four-step distrust procedure; five plan-comparison classes; five cause classes | gigio-review-results | Verification | Automated judges scored at or below 0.65 AUROC in the material surveyed | Keep |
| Fresh-context review, no self-review | gigio-review-results | Verification (anchoring) | Observed judge failures under shared context | Keep |
| **`CLAUDE.md` → `AGENTS.md` bridge as the compaction-survival path** | gigio-project-setup | **Measured workaround** | Harness docs, confirmed 2026-07-25 | **Re-verify on every harness update** |
| Direction evidence batches at review; execution records and continues | gigio-execute-plan, gigio-review-results | Boundary | User-set policy 2026-07-26: in creative and research domains the artifact rewriting the intent is the main path, and per-finding stops would turn the approval boundary into a bottleneck | Keep; re-examine at pilot closeout against the proposal count |
| Explicit worktree mechanism and directory choices win; otherwise Git creation stays under the repository's `.worktrees/` directory | git-worktree-setup | Boundary | User-set policy 2026-08-04: native ownership changes lifecycle behavior, while an unrequested sibling or global path expands the filesystem scope | Keep |
| Authenticated `gh` user is the default PR assignee; another assignee requires an explicit user choice | draft-pr | Boundary | Assignment determines who owns follow-up work; repository context alone is not authority to assign another person | Keep |
| Pack-internal references are unconditional | all skills | Storage (distribution simplicity) | The pack ships as one unit | Keep |

Two rows are measured workarounds. They are the only rows expected to die.

## Generation audit

Adopting a new model generation, or a major harness overhaul, is an **audit
event**, not a routine upgrade. Run this and append the result to the deletion
record below:

1. **Re-measure every measured-workaround row** above. If invalidated, delete
   the rule from the skill and record it.
2. **Collect removal candidates** — steps the lead demonstrably did not need
   during real use. Delete generic scaffolding the target model succeeds
   without.
3. **Check knowledge-shaped skills for depreciation.** Skills that carry
   domain knowledge lose value as models absorb it. Refresh or retire.
4. **Confirm no growth** — skill bodies stay within 400–2,500 tokens, and
   always-loaded routing stays at two lines.

## Deletion and compression record

**2026-07-26 — failure-routing table compressed.** The execution skill's
five-class failure table was reduced to its contract core (no same-prompt
retry, cap of two, plan defects go back to the human). The three diagnostic
rows prescribing a remedy per cause were judged cognitive map and deleted.

**2026-07-26 — repetition removed from the core four.** Seven instances where
a Gotcha restated the body were cut, keeping the statement only where the
reasoning lives. Replacement Gotchas carry non-repeating failure shapes only:
dispatch honesty, found-during scope, self-review anchoring, check-coverage
gaps.

**2026-07-26 — upstream and execution scan.** Removed: a three-lens persona
device in `deep-interview`, replaced with three outcome checks; duplicate
approval-boundary statements in `find-unknowns` (3→1) and its single-technique
rule (3→2); a field list in `small-model-handoff` replaced by a gate table,
with its plan-fixing rule 3→1 and peer-executor prohibition 3→2; the Common
Scenarios section in `orchestrate-subagents` (a third enumeration of the same
ground); a negated restatement plus three repeated Gotchas in
`fable5-model-routing`; five pure restatements across `session-handoff`,
`git-worktree-setup`, and `draft-pr`.

*Reviewed and kept:* the Quick Start ↔ detail two-tier structure throughout
(progressive disclosure — an 80% path plus detail, not the same rule twice);
`commit-and-push`'s repeated "preserve unrelated changes" (each pipeline stage
applies it at a different point); body+Gotcha pairs where each half carries
something the other does not.

**2026-07-26 — dual review** (two independent reviewers, different model
families). *Fixed:* the plan template had workers recording their own results
entries, contradicting the worker preamble's "no writes outside owned files"
and the no-overlap principle — recording moved to the lead alone;
`session-handoff` gained a NOT-for boundary so sibling discrimination runs
both ways.

*Reviewed and kept:* (1) generalizing single-message dispatch and worker
non-inheritance across harnesses — both are harmless no-ops where unmeasured,
so adding a harness gate costs more than it returns; (2) the unconditional
reference from `find-unknowns` to `fable5-model-routing` — the target skill's
own entry gate excludes harnesses where it doesn't apply; (3) the "not
installed" fallback line in the plan template — load-bearing for a worker that
cannot inherit skills and consumes the plan file raw; (4) legacy fixtures
inside migrated skills — covered by the preserve-original-strengths rule; the
four newly authored core skills have none.

**2026-07-26 — first-install refinements** (evidence from the two pilot
installs, before any plan has run). *Fixed:* the setup audit never checked
whether the intent layer was committed, and one real install passed the audit
with every file uncommitted — a committed-state check was added and graded
blocking; completion evidence assumed git-tracked files, failing any task
whose deliverable is a gitignored artifact (a run's report, generated data) —
evidence now names the artifact for untracked outputs; review conflated
"unverifiable" with acceptance that names the owner's judgment as its check —
the latter is now a separate awaiting-owner-judgment list. All three follow
from rules already in force (trust-only-committed, acceptance axis); none
anticipates unmeasured behavior.
