# Project Wiring

Use this reference when setting up or updating project instructions. Both terminology skills apply on every task by default in this pack. Put that policy in the actual instruction entry point so it does not depend solely on automatic skill selection.

Read the actual project instruction files and their include or bridge relationships. Adapt the [instruction example](../assets/project-instructions.md) to the canonical glossary's real location, then add the smallest pointer and behavior rule that reaches the agents the project uses. Resolve links relative to each instruction file. Preserve unrelated rules and avoid competing copies of the full glossary.

For a project already using `AGENTS.md` with a `CLAUDE.md` bridge, put the shared policy in `AGENTS.md` and preserve or repair the existing bridge. If the project maintains independent instruction files, keep their terminology obligations consistent through a shared reference. Use the exact filenames supported by the project; a similarly spelled file does not establish that any harness will load it. For another harness, follow its configured instruction entry point and verify that it references the policy. Do not promise universal loading or invent hooks.

The standing rule must name both `use-terminology` and `curate-terminology`, require reading at task start, and cover English-first terms, verbs, collocations, and explanations. It grants correction of confirmed in-scope problems and maintenance of the related reference when encountered, without another wording request. Reuse existing entries and leave records unchanged when nothing relevant needs updating. An explicit read-only task still limits the result to findings and proposed corrections.

This is a deliberate pack policy for the terminology pair. It does not activate unrelated planning, model changes, publication, or repository-wide audits. A pointer in prose is a project instruction, not a deterministic enforcement mechanism. Skill installation alone cannot prove that every host will load it; do not claim runtime behavior without observing it.

Check that every referenced file exists, each configured instruction entry point reaches the canonical policy, and the rule does not contradict the user's requested scope. Describe the configured path accurately; static inspection does not prove future runtime compliance. `gigio-project-setup` owns broader project setup when requested, while this skill owns the terminology portion.
