# Decision Log

Direction changes, in the order they happened. Each entry uses the same four
fields the pack asks of every deviation:

**what the plan said → what reality revealed → the conservative choice taken →
when to revisit.**

The point of keeping the reversals is that they are the expensive part. Most
entries below record something being thrown away.

---

## Central controller architecture rejected

- **Plan:** adopt one root controller from an existing workflow system and
  layer a language router, an evidence contract, and an executor compiler
  beneath it.
- **Reality:** building a harness and slotting the real harnesses into it was
  the wrong shape. The framing of a controller owning authority was already
  too much. Agent skills plus concepts common to every harness is the ceiling.
- **Choice:** keep the goals (plan durability, drift propagation, verification,
  delegation to weaker models). Demote the controller candidates from
  installation to sources worth mining for artifact shapes. Replace the
  controller pilot with a much cheaper probe: apply skills-only conventions to
  one real task.
- **Revisit:** if skills-only discipline repeatedly fails in real projects,
  widen ambient enforcement first — do not reopen the controller question.

## Restated the original request

- **Plan:** the discussion had drifted from controller pilot to skills-only to
  vocabulary cleanup.
- **Reality:** the original request had been four capability items all along,
  and controller adoption was a means nobody had asked for.
- **Choice:** reuse the research output as raw material for the actual four
  items rather than as a plan of record.
- **Revisit:** re-check the four items against a real project after building.

## Resume automation scoped down

- **Principle:** for the specific problem of resuming work, high-quality
  records make deterministic restore machinery unnecessary — the model
  reconstructs from the record. This is not a general "records first"
  principle.
- **Effect:** invalidates resume automation as a selling point in the systems
  that lead with it, while leaving the value of their record formats intact.

## Survey verdict: no external pack adopted wholesale

- **Result:** every candidate came back mine-only. Recurring disqualifiers were
  bundled hooks, broad auto-triggering descriptions, commands that presuppose
  each other, and record quality no better than a hand-written convention.
- **Decision:** the answer to the original request is a hand-written record
  convention, with mining sources identified at file level.
- **Revisit:** if a real cycle fails acceptance, strengthen convention fields
  first, then ambient enforcement. No controller reconsideration.

## Premise correction: the problem is supervision visibility, not planning discipline

- **Plan:** the record convention assumed a "next big project starts" trigger.
- **Reality:** the big projects were already running, model-driven and
  continuous. The actual pain was different: (1) no way to notice when the
  instruction was wrong or the model made a mistake, and (2) work evaporating
  with the session instead of accumulating structure. The only tool in real
  daily use was the one that paid off immediately, in flow.
- **Choice:** look for structure on the way *out* (audit, with records as a
  by-product) rather than on the way *in* (planning).
- **Revisit:** if records still don't accumulate after that, revisit ambient
  enforcement.

## Standalone audit skill discarded

- **Plan:** treat `unknowns pass → plan seed → ambient upkeep → audit → receipts`
  as a finished delegation loop, run one cycle on a real repository, then
  promote it.
- **Reality:** the audit skill was deleted by hand. Not because reviewing has
  no value — because a lone skill whose role before and after is invisible has
  no value. The assembly's real usage count was zero, and the documentation had
  recorded it as "built" far too early.
- **Choice:** do not restore or improve it. Define the connected map first:
  direction forming → a user-owned source of truth → readiness judgment →
  execution → intent-based review → the same source updated. Strong models run
  autonomously on thin instruction; detail is added only when handing
  direction-resolved mechanical work to a weaker executor.
- **Revisit:** after one real project has run both a strong-model path and a
  constrained weak-executor path from the same source, judge what else is
  needed.

*This entry is the origin of the pack's "nothing is recorded as done before it
has been used" rule.*

## Loop correction: remaining judgment means not ready

- **Plan:** under "choose an execution mode," one branch was "judgment remains
  → strong model and human explore."
- **Reality:** remaining judgment does not mean picking an executor type. It
  means the work is not ready to execute and must go back to direction forming.
  And what is needed after execution is not code review or mechanical
  verification but a comparison of intent, background, goals, decisions, and
  non-goals against the actual result.
- **Choice:** correct the topology to `direction forming ↔ work map → readiness
  judgment → execution → intent-based review → map update`. Review results
  route to direction forming (premise problem), re-execution (execution
  problem), or map update (accepted).
- **Revisit:** confirm in a real project that readiness judgment actually blocks
  unresolved judgment, and that review doesn't collapse into output inspection.

## Single-agent assumption dropped; parallel fan-out promoted into the plan structure

- **Plan:** the unified design assumed the planning skill writes a plan and the
  same agent executes it, with delegation handled separately by a six-step
  strong→weak protocol.
- **Reality:** the default working style is aggressive parallel subagent
  fan-out, and a plan written for that is structurally different from one that
  isn't. Re-survey found: mature references all separate lead from worker;
  parallelism comes from the plan file's data structure (stage / prerequisite /
  owned files), not prompt wording — measured, instruction alone produced zero
  multi-dispatch; conflict prevention is planning-time ownership partitioning,
  not locking, and one system's lock machinery turned out to be dead code. The
  six-step protocol's step 4 also duplicated an already-installed skill
  verbatim, and a supporting claim from an earlier wave was found to be a
  misreading.
- **Choice:** add four lines per work item (stage / prerequisite / owned files /
  delegable) as **facts rather than instructions**, so the same file survives
  both solo execution and parallel dispatch. Move the execution contract into
  the planning skill and discard the six-step protocol. Delegate decomposition
  and merge by name to the orchestration skill. Reject large-abstraction
  designs and write down "markdown a human can read and fix by hand" as a
  principle.
- **Revisit:** observe real out-of-scope-edit requests and blocked reports in
  pilots before fixing a reassignment policy.

## Execution split into its own explicitly invoked skill

- **Plan:** keep execution as a section inside the planning skill; assume
  "plan file plus ambient guidance" is enough to run on.
- **Reality:** the operating principles you want at the moment of execution were
  scattered across global skills, so "read the plan and figure it out" gave no
  guarantee they would fire together. Of ten implementations read, nine
  separated execution into its own invocation unit; the one that didn't was a
  1,000-line outlier. One system explicitly forbade execution from its
  always-loaded skill; another had 435 always-loaded lines and no invocation
  verb — knowledge present, activation impossible.
- **Choice:** create the execution skill. Four reasons to separate: the two
  postures are incompatible (planning asks and stops; execution does not stop —
  merged, they average out); preflight cannot live inside the plan file; a new
  session must be able to enter alone and survive compaction; resume logic
  belonged to the execution side in every reference that had it. Activation is
  triple: two lines of ambient routing, a one-line pointer in the plan file
  header, and the description boundary.
- **Revisit:** watch activation rate in pilots — does the plan-file header
  pointer actually trigger a new session — and how often preflight catches a
  mismatch.

## Extended survey: no confirmed decision overturned

- **Result:** a wider sweep of local and newly cloned systems overturned nothing.
  It produced additions: plan-time SHA and freshness check, forbidden-files with
  mandatory reason, three prerequisite edge types, an append-per-round execution
  log, two verification layers (task acceptance plus project-wide criteria), and
  a decisions section carrying a no-re-litigation rule.
- **Counter-evidence gained:** one system's own admission that a dispatch which
  isn't real makes progress reports fiction supports the built-in-delegation-only
  decision. Another's self-abandonment of its orchestration layer supports
  "the execution skill does not redo decomposition and ordering."
- **Revisit:** no successful instance of parallel *writing* was found anywhere
  in the survey — only read-only parallelism or unverified claims. Measure the
  actual benefit in pilots.

## Weak-executor path gets explicit activation and a guidance bundle

- **Plan:** hand detail-heavy prompts to weak executors; keep strong models thin.
- **Reality:** task-level detail alone may not be enough for a weak model —
  over-implementation, scope expansion, reimplementing what exists, and skipped
  verification also need addressing. But applying that same discipline to a
  strong model damages its autonomy.
- **Choice:** the strong path stays the default. The weak path and its guidance
  bundle activate **only** when the user explicitly chooses a lower-capability
  executor. Never classify automatically by model name, price, or speed. Do not
  adopt any always-on enforcement, and do not let the bundle substitute for
  intent-based review.
- **Revisit:** confirm in a real weak-model pilot that the bundle reduces
  over-implementation and missing evidence, that packet-writing cost stays below
  the saving, and that the rules don't leak into the strong path.

## Renamed for purpose and outcome; migrated skills preserved

- **Plan:** two naming tiers plus three renames were assumed sufficient.
- **Reality:** review found the names still abstract — purpose and outcome were
  not in the name. Skills should follow the pack's own skill-authoring reference
  rather than a norm invented for the pack. And the migrated skills were already
  individually well-built; combining them into a pack must not erode that.
- **Choice:** fix the naming principle as "purpose and outcome in the name" and
  rename accordingly. Author the core four to the skill-authoring rules
  (decision rules over transcripts, 400–2,500 tokens, sibling-discriminating
  descriptions). Edit migrated skills minimally — one to four focused edits each,
  adding interlocks only, never rewriting the body.
- **Revisit:** watch for misfires between planning and execution in pilots.

## "Contract steps, not cognition steps" adopted

- **Plan:** the pack was considered finished; next was piloting.
- **Reality:** a strong model follows a badly designed procedure just as
  faithfully as a good one, so the opportunity cost of an unnecessary step grows
  every generation. For a pack that had codified a large number of prescriptions,
  that is a structural threat. A self-audit found roughly thirty real violations.
- **Choice:** keep the structure — the four-station pipeline is exactly the
  auditable fixed pipeline the rule endorses, and the pack's four sources of
  value (storage, boundary, verification, concurrency) are orthogonal to model
  strength. Write the principle down in the repository rules, create the
  [rule ledger](rule-ledger.md), and run an improvement pass across every skill
  (detection delegated, judgment and edits kept with the lead). Add "steps the
  lead demonstrably did not need" to the pilot observation list.
- **Revisit:** re-verify the ledger's measured-workaround rows at the next model
  generation.

## Pack cut from 24 skills to 13

- **Plan:** move every development-related skill — the work loop, craft skills,
  and pack-maintenance meta skills.
- **Reality:** review of the assembled catalog showed the pack had swallowed more
  than it should. Craft and meta skills are independent of the work loop.
- **Choice:** cut to 13 (four core, two discovery, four execution support, three
  outbound). Eleven skills returned to their original repository as canonical
  home. The cut line is clean — zero references from the remaining 13 to any of
  the 11. General-purpose improvements made during the session were ported back
  to the originals rather than lost; pack-specific modifications were discarded.
- **Revisit:** observe in pilots how often the lead actually calls craft skills
  from outside the pack.

## Name settled: gigio-pack

- **Plan:** narrow metaphor-word candidates from a corpus of 500+ references.
- **Reality:** every external word was rejected as odd. The cause was
  over-optimizing for metaphor precision, which surfaced only unfamiliar words —
  while the reference points the owner actually admired were all familiar words.
  One leading candidate was disqualified because it reads as an unrelated word
  in Korean; another was already taken by a product in the same category. The
  only word that cannot feel awkward is the owner's own handle.
- **Choice:** `gigio-pack`, with `gigio-` as the prefix for the four core skills
  only. Three renames for clarity: the orchestration skill gained a verb;
  the session handoff skill adopted the term used by a major agents SDK; and the
  weak-executor skill was renamed to restore the original intent — a handoff to a
  less capable AI, not to an in-harness worker. The two handoff skills are now a
  deliberate pair, with the target in the name.
- **Revisit:** at public release, reconsider — eponym to product name is a
  standard rebranding path.

## Design record separated from the published repository

- **Plan:** publish the repository with its full working record.
- **Reality:** the record is candid Korean working material containing local
  filesystem paths, private project names, and workplace-boundary notes. A
  privacy review confirmed the skills themselves were clean and the exposure was
  confined to that directory.
- **Choice:** keep the raw record local and unpublished. Distill its durable
  content into three public documents — [principles](principles.md),
  [rule ledger](rule-ledger.md), and this log — plus a
  [prior-art](prior-art.md) summary, so that improving the pack later does not
  require digging through chat sessions. History was rewritten so the record was
  never published.
- **Revisit:** if the pack is ever handed to someone else, these four documents
  are what they get; check whether they are enough to make a change safely.

## Acceptance separated from the check command

- **Plan:** every task carries a `check` command, and a task whose check you
  cannot state is not plannable yet.
- **Reality:** the loop had quietly taken the shape of repository work. The four
  core skills carry about thirty lines of test, build, and commit vocabulary and
  none for research or open-ended work, while `find-unknowns` already classifies
  a result as executable or comprehension-checked and had nowhere downstream to
  send that classification. Two domains invert the rule outright. An
  experiment's check *is* the measurement, so a negative result is the
  deliverable rather than a defect to repair, and retrying it with a stronger
  model is the wrong response to a hypothesis that did not hold. Work judged by
  feel has an acceptance and no command at all. The
  [principles](principles.md#plans-are-written-for-a-reader-with-no-memory) page
  had already required acceptance and verification as separate axes; the plan
  template had collapsed them into one field.
- **Choice:** add `acceptance` to the task fields and keep `check` as
  verification only. Treat a check that ran with its acceptance met as done even
  when the result is negative. Classify work built as planned whose result still
  misses the goal as a direction finding rather than one of the review's three
  lists. No new skill — a fourteenth name costs more than the fit it buys while
  none of this has been measured.
- **Revisit:** at the pilots, one of which should be non-engineering so the
  experiment case is measured rather than argued. Deliberately left untouched:
  completion still requires changed owned files under git, and file ownership is
  still the only parallel split. Both are wrong for a configuration sweep, where
  the unit of work is a run and sibling runs share an output directory — change
  them from a real run, not from this entry.

## Direction changes batch at the review station

- **Plan:** intent contradiction discovered mid-run stops the work and routes
  to the user — renegotiation as an exceptional event.
- **Reality:** the two pilot installs showed that outside ordinary engineering
  the flow reverses: the artifact rewrites the intent as the main path. One
  pilot opened with six of its seventeen settled decisions already superseded
  by play; the other's methodology is literally that observation selects the
  next study. Per-finding stops would make the human-owned boundary a
  bottleneck or teach sessions to route around it.
- **Choice:** user-set policy. Execution records intent contradictions in the
  Run log and keeps going unless continuing is certain waste; the review
  station batches all direction findings into one proposed top-half amendment
  diff, each line backed by the play or observation behind it, settled by a
  single approval. The boundary keeps its authority; it loses its per-event
  interruption cost.
- **Revisit:** pilot closeout — count amendment proposals per review. If the
  user keeps intervening mid-run anyway, the batching is theater; revisit.

## Git-created worktrees stay inside the repository

- **Plan:** prefer a harness's native worktree feature whenever it exists and
  send manual Git worktrees to another untracked location when the repository's
  local directory is not already ignored.
- **Reality:** the fallback permitted sibling directories such as
  `<repository>-worktree`, which scattered workspaces across the parent folder.
  A named branch created with Git remains usable by ordinary GitHub PR discovery;
  native creation mainly adds harness-owned placement and lifecycle behavior.
- **Choice:** explicit mechanism and directory preferences win. With no stated
  preference, create a Git worktree under the repository's `.worktrees/`
  directory and use the local Git exclude file when needed. Never leave the
  repository merely to avoid a tracked ignore edit. Choose native creation when
  the user asks for its handoff, restoration, or cleanup behavior.
- **Revisit:** if either primary harness makes manually linked worktrees unable
  to expose ordinary branch and PR state, record the observed version and move
  only that behavior into a dated harness-specific rule.

## PR bodies optimized for first-time readers

- **Plan:** use a prose-led `Summary` followed by `Validation`, with local
  checks listed directly in the body.
- **Reality:** PRs produced from active sessions assumed context that reviewers
  did not share, grew into long narratives, and repeated command lists or test
  output already represented by CI. The extra validation text did not help a
  reviewer decide whether the change was sound.
- **Choice:** repository templates remain authoritative. Without one, use
  `Context` and `Changes` as the two-section fallback. Add `Validation` only
  for manual results CI cannot prove or a material CI caveat; keep live CI
  status in the checks interface and collapse long supporting details. Add
  reviewer notes, user impact, migration, rollout, performance, or screenshots
  only when the change triggers them. The body must stand alone for a reader
  without the authoring session.
- **Revisit:** if reviewers repeatedly need another field across unrelated
  repositories, consider it for the fallback. Keep project policy in repository
  templates rather than growing the shared default.

## Skills gated to explicit invocation

- **Plan:** descriptions would carry a `Use when …` trigger precise enough that
  the harness would open the right skill at the right moment, and C4 ("explicit
  invocation plus ambient prose only") would hold because the pack shipped no
  hooks or daemons.
- **Reality:** C4 constrained the mechanism and left the trigger alone. Several
  descriptions named a *situation* rather than a request — "sizable work needs
  a written plan", "a large task has independent workstreams", "the user starts
  substantial work in territory they don't know well" — and a situation is
  something the model decides it is looking at. In daily use the pack activated
  across conversations that had asked for none of it, research and other
  non-engineering talk included, where an answer was the whole job. The
  prior-art survey had already recorded broad auto-triggering descriptions as a
  disqualifier in other packs, and this pack had shipped the same defect.
- **Choice:** state the gate in all 13 descriptions. A skill opens when the
  user names it, when the user asks for what it does, or when another pack
  skill name-calls it inside a run the user already started — and on nothing
  else. Each description carries the rule in its own words, since the harness
  reads them one at a time. Accept the loss: a user who would have benefited
  from a pass they did not know to ask for will not get it, which is cheaper
  than charging every conversation for one it did not want. Skill bodies are
  unchanged apart from `gigio-project-setup`, whose installed `AGENTS.md` block
  described routing as a standing instruction to plan sizable work.
- **Revisit:** if a pilot shows the pack going unused where it clearly would
  have paid off, widen the wording of the specific skill's request forms —
  never restore situational triggers, and never add an always-on instruction
  that recreates them from outside the pack.

## Invocation gate narrowed from thirteen skills to eight

- **Plan:** state the gate in all 13 descriptions, on the reasoning that
  deciding a procedure runs is the user's call in every case.
- **Reality:** applied to all 13 it was too wide. Five skills cost nothing when
  they open uninvited. Four of them — `deep-interview`, `commit-and-push`,
  `draft-pr`, `git-worktree-setup` — already described a request rather than a
  situation, so a harness matching the description was already the user asking,
  and the added gate text bought nothing. The fifth, `find-unknowns`, was the
  real error: gating it removed the one case where an unrequested pass is worth
  more than it costs, since it exists to fire before the user knows to ask and
  its worst misfire is a paragraph that can be skipped. The complaint that
  started this had never been about that skill.
- **Choice:** restore the five descriptions to their pre-gate text and keep the
  gate on the eight whose misfire lands on disk or on the bill — the four core
  skills, `session-handoff`, and the three that change who executes the work
  (`orchestrate-subagents`, `small-model-handoff`, `fable5-model-routing`). The
  deciding question is not who owns the decision but what an unwanted opening
  costs. `find-unknowns` is recorded as an explicit exception, the only skill
  here allowed a situational trigger.
- **Revisit:** if `find-unknowns` starts opening on conversations that only
  wanted an answer, narrow its situations rather than gating it, and check the
  always-on instruction layer outside this pack first — an `AGENTS.md`
  paragraph mandating the same behavior outranks any description.

## PR publication made forge-aware

- **Plan:** route Forgejo publication through its REST API or authenticated web
  UI because the `forgejo` binary is a server administration CLI and Gitea's
  `tea` does not prove Forgejo compatibility.
- **Reality:** the Forgejo project now publishes the `fj` user CLI. Version
  0.6.0 creates, views, edits, assigns, checks, and merges PRs, including an
  explicit squash method. It uses API authentication separate from Git
  transport. Its create command has no draft flag, body edit has no body-file
  option, draft detection recognizes `WIP:`, and merge has no confirmation
  prompt.
- **Choice:** resolve the provider plus exact head and target repositories
  before mutation. Keep commit and push provider-neutral, use `gh` for GitHub,
  and require authenticated `fj` for Forgejo. Create Forgejo drafts with a
  verified `WIP:` title, use exact `owner/repo#index` references for management,
  and allow squash merge only after a separate explicit merge request and
  remote state gates. On GitHub, preserve `gh`'s native draft, body-file,
  required-check, head-OID match, and merge-queue behavior. Never install or
  authenticate a CLI implicitly. Delete a head branch only on explicit request.
- **Revisit:** simplify the adapter when `fj` exposes a native draft flag,
  body-file editing, structured output, a bounded check wait, or a merge
  confirmation mode.

---

## Still open

| Item | Default | Decide when |
| --- | --- | --- |
| Plan directory name | `.plans/` | On first friction |
| Where to plant intent for non-repository projects | Same convention, project folder | First non-repository application |
| Information boundary for work-context projects | Undecided | First such application |
| Deferred concepts (three-state memory transitions, hard notepad budgets, verified-vs-reported markers) | Not adopted | If real usage shows the corresponding problem |
| Experiment-shaped work beyond the basics: run manifests, seeds, quota fields, mid-sweep triage | Runs are tasks owning their output directory (adopted 2026-07-26); nothing further | First real experiment loop — one pilot's planned three-model comparator sweep is exactly this shape |
| Decisions-digest growth in high-reversal domains: one pilot opened with 17 decision rows plus 6 supersessions on day one, and no compression or retirement rule exists | Keep appending, supersede never delete | First time loading the table becomes a burden |
| Whether batched direction amendments actually hold — or the user keeps intervening mid-run regardless | Policy adopted (see "Direction changes batch at the review station"); count proposals per review | Pilot closeout |

**Not yet piloted.** Nothing in this pack is marked done until two pilot
projects pass. Pilots measure four things: whether parallel writing actually
pays off, whether the plan file carries enough for handoff between workers,
which steps the lead demonstrably did not need — a removal list, not a success
list — and what the acceptance field actually gets filled with outside ordinary
code work.
