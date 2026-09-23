# Repository Responsibilities and Migration

This change keeps the three repositories independent. Gigio maintains project context; agent-skills maintains reusable execution and production capabilities; research-credo maintains research methods.

## Moved packages

| From Gigio Pack | Destination |
| --- | --- |
| orchestrate-subagents | agent-skills/skills/development/orchestrate-subagents |
| small-model-handoff | agent-skills/skills/development/small-model-handoff |
| fable5-model-routing | agent-skills/skills/development/fable5-model-routing |
| git-worktree-setup | agent-skills/skills/development/git-worktree-setup |
| commit-and-push | agent-skills/skills/development/commit-and-push |
| draft-pr | agent-skills/skills/development/draft-pr |
| python-coding-standards | agent-skills/skills/development/python-coding-standards |

Names and helper resources are preserved. No duplicate discoverable compatibility packages remain in Gigio. Existing local project records are not migrated or deleted.

## Coordinated publication

Review the destination packages before merging source removals. The companion agent-skills PR also moves evaluation-operations and internal-source-research into research-credo. Merge research-credo first, then the agent-skills changes, then Gigio. Update installations only after the selected revisions are available, or explicitly install the reviewed PR branches.

Use the existing install-skill-pack workflow to add the moved names from the destination repository and verify that the installed source metadata points there. Same-name installs may overwrite the old deployed copy: preserve local customizations first. A source removal alone does not remove an installed skill or update its tracked origin.

Installations are separate from PR publication. Do not uninstall first, point to an unmerged main, or install two competing copies of the same name.

## Existing plans and shared documents

Old plan fields remain readable. No migration script rewrites user goals, results, or active jobs. New rounds use the current understanding and next decision rather than demanding all future stages.

General document methods live in technical-report-writing. share-internal-doc was retired on 2026-09-24; its recipient, source-access, sharing-pass, and delivery rules moved verbatim to that writer's `references/sharing-and-delivery.md` in agent-skills. Remove the installed package with the Skills CLI; a request that names share-internal-doc is served by the writer. Preserve existing project source workflows and useful figures.
