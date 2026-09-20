# Gigio Pack

Keep a project's purpose, direction, current understanding, and next decisions available across sessions, models, and harnesses.

A project can be research, model development, dataset review, a benchmark, a document, or software. It can span repositories and servers. Progress may be a finding or a better-supported decision without a code change.

## Work from the next decision

PROJECT.md or an existing equivalent holds user-owned direction and an agent-maintained digest of current understanding. Plans detail the next useful work, then adapt to findings. Existing experiment records, research indexes, and operational logs keep their own jobs.

Fast follow-up checks within the current question and allowed resources can proceed. Changes of direction and long new work, such as a two-to-three-day activity, need a user decision unless already authorized. Cost, access, and other project limits still apply.

Use only the skills the request needs. Setup, planning, execution, and review are distinct responsibilities, not a mandatory sequence for every task.

## Skills

| Skill | Responsibility |
| --- | --- |
| [gigio-project-setup](skills/gigio-project-setup/) | Establish or audit purpose, direction, constraints, current understanding, and source locations |
| [gigio-write-plan](skills/gigio-write-plan/) | Detail the work needed for the next decision |
| [gigio-execute-plan](skills/gigio-execute-plan/) | Execute, interpret findings, and continue within the established grant |
| [gigio-review-results](skills/gigio-review-results/) | Assess progress and whether the next decision is supported |
| [find-unknowns](skills/find-unknowns/) | Resolve consequential gaps before expensive work |
| [deep-interview](skills/deep-interview/) | Interview when sustained requirements discovery is explicitly wanted |
| [session-handoff](skills/session-handoff/) | Give the next session the current understanding, sources, and next action |
| [share-internal-doc](skills/share-internal-doc/) | Apply the document writer, check recipient suitability and source access, and deliver when authorized |
| [curate-terminology](skills/curate-terminology/) | Maintain project definitions, expressions, and source records |
| [use-terminology](skills/use-terminology/) | Apply those accepted terms and expressions |

## Related capabilities

[agent-skills](https://github.com/gigio1023/agent-skills) supplies harness use, delegation, coding, Git delivery, writing, and visualization. [research-credo](https://github.com/gigio1023/research-credo) supplies research direction, literature, experiments, datasets, evaluation methods, and operations. Their methods can be used directly or within a requested Gigio project.

The repository split separates responsibility without prescribing a fixed sequence. Relevant companions are used when available; missing optional tooling does not require another framework or an unrequested install.

## Install

Install selected skills, or this pack's ten skills, for the intended agents:

```bash
npx --yes skills add 'gigio1023/gigio-pack#main' --global --agent claude-code codex cursor --skill '*' --yes
```

Publication does not refresh installed copies. Use install-skill-pack when an installation or update is requested. During the repository migration, install from a merged revision or the explicitly selected PR branch; main does not include an open draft.

## Migration

Seven tool-oriented skills move to agent-skills with their existing names: orchestrate-subagents, small-model-handoff, fable5-model-routing, git-worktree-setup, commit-and-push, draft-pr, and python-coding-standards. See [migration](docs/migration.md) for installation-source changes and coordinated merge order.

Old plans remain readable. Their known dependencies and completed records still matter; future stages can be revised as findings arrive. No bulk conversion of project files is required.

## Maintenance

Skills and project records are readable Markdown. The pack adds no daemon, database, or required runtime. Keep original data and confidential work out of the public skill sources.

Read [principles](docs/principles.md), [rule ledger](docs/rule-ledger.md), [decisions](docs/decisions.md), and [contributing](CONTRIBUTING.md) when changing the pack. Apply the terminology pair under its standing policy without artificial writes or unrelated surveys.
