# Gigio Pack repository guidance

Maintain the project-context and adaptive-work skills described in README.md. Current principles are in docs/principles.md; current load-bearing rules are in docs/rule-ledger.md. Historical decisions retain provenance but do not override later user-approved changes.

## Authoring

- Public skills and documentation are English. Keep Markdown prose as natural paragraphs without fixed-column source wrapping.
- Use established field language. Do not invent framework terminology or require a fixed thinking sequence.
- Keep skills self-contained with colocated resources. References are loaded for a named decision, not all at once.
- Preserve original records, unrelated changes, and private design material. docs/design/ is private historical input, not publication content.
- Apply use-terminology and curate-terminology under their standing policy. Use an existing project terminology index; do not create an artificial glossary for a maintenance task with no new terminology.
- Update README, affected references, instructions, and current rule documentation together when responsibilities change.
- Document craft, explicit editorial defaults, and internal sharing (recipients, source access, sharing pass, delivery) belong to copydesk in agent-skills; the pack's share-internal-doc was retired into it on 2026-09-24.
- No runtime framework, daemon, mandatory project database, or model-evaluation scaffolding in skill payloads.

## Work and authority

A project can span repositories and non-code work. User-owned direction is separate from maintained findings. Plan only through the next useful decision, adapt bounded work to results, and ask before a direction change or long new activity unless already authorized. Preserve narrower resource and side-effect limits.

The four core skills have separate request triggers. A request covering several steps already grants those steps; do not require repeated confirmation. Relevant specialist skills can be used within the task. Delegation still follows the user's request and the active harness policy.

Harness, Git, delegation, and Python helpers are maintained in agent-skills. Research methods are maintained in research-credo. Do not restore local copies to repair a missing installation.

## Validation and publication

Discover all ten packages with the Skills CLI, validate their metadata and resource links, and check changed templates and examples. Static review does not demonstrate model behavior. Model comparisons require a corresponding request.

Commit only when requested; a PR request includes scoped commits and push. Use conventional English titles and concise PR bodies. Non-trivial commits explain Context, Changes, Results, and Validation. PRs are draft by default. Publication does not authorize merging, global installation, or cleanup of unrelated worktrees.

## Tests

A test written after the code, with expected values read off that code, repeats the implementation: it passes by construction, misses the bugs it shares with the code, and breaks on every refactor. Do not write such tests unless the user asks for a specific one.

- Verify features end to end. Run the real entry point on real or fixed input and leave an artifact another person can rerun and compare, such as an output file, log, report, or screenshot. Give the command and the artifact path in the final message.
- When a unit needs an isolated test, first list the ways it can fail, take expected values from the spec or a hand calculation, and only then write the code.
- A bug fix may add one test that reproduces the bug and fails before the fix.
- Keep or add a test only if losing it would let a security, money, data-loss, or reported-number bug ship unnoticed and no end-to-end run covers it.
- If a refactor that keeps behavior breaks a test, the test was checking implementation. Delete it instead of rewriting it and list it in the PR.
- Do not test constants, prompt or message strings, output formatting, internal helpers, or fakes built for the test itself.

End-to-end path here: the Skills CLI discovery and validation in Validation and publication above. Skill payloads carry no test scaffolding.
