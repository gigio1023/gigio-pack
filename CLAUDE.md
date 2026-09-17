# Gigio Pack repository guidance

Maintain the project-context and adaptive-work skills described in README.md. Current principles are in docs/principles.md; current load-bearing rules are in docs/rule-ledger.md. Historical decisions retain provenance but do not override later user-approved changes.

## Authoring

- Public skills and documentation are English. Keep Markdown prose as natural paragraphs without fixed-column source wrapping.
- Use established field language. Do not invent framework terminology or require a fixed thinking sequence.
- Keep skills self-contained with colocated resources. References are loaded for a named decision, not all at once.
- Preserve original records, unrelated changes, and private design material. docs/design/ is private historical input, not publication content.
- Apply use-terminology and curate-terminology under their standing policy. Use an existing project terminology index; do not create an artificial glossary for a maintenance task with no new terminology.
- Update README, affected references, instructions, and current rule documentation together when responsibilities change.
- No runtime framework, daemon, mandatory project database, or model-evaluation scaffolding in skill payloads.

## Work and authority

A project can span repositories and non-code work. User-owned direction is separate from maintained findings. Plan only through the next useful decision, adapt bounded work to results, and ask before a direction change or long new activity unless already authorized. Preserve narrower resource and side-effect limits.

The four core skills have separate request triggers. A request covering several steps already grants those steps; do not require repeated confirmation. Relevant specialist skills can be used within the task. Delegation still follows the user's request and the active harness policy.

Harness, Git, delegation, and Python helpers are maintained in agent-skills. Research methods are maintained in research-credo. Do not restore local copies to repair a missing installation.

## Validation and publication

Discover all ten packages with the Skills CLI, validate their metadata and resource links, and check changed templates and examples. Static review does not demonstrate model behavior. Model comparisons require a corresponding request.

Commit only when requested; a PR request includes scoped commits and push. Use conventional English titles and concise PR bodies. Non-trivial commits explain Context, Changes, Results, and Validation. PRs are draft by default. Publication does not authorize merging, global installation, or cleanup of unrelated worktrees.
