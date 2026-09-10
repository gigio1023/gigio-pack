# Project Wiring

Use this reference only when the user requests mandatory ongoing terminology use or asks to update that existing policy. Installing either terminology skill does not make it always active.

Read the actual project instruction files and their include or bridge relationships. Adapt the [instruction example](../assets/project-instructions.md) to the canonical glossary's real location, then add the smallest pointer and behavior rule that reaches the agents the project uses. Resolve links relative to each instruction file. Preserve unrelated rules and avoid competing copies of the full glossary.

For a project already using `AGENTS.md` with a `CLAUDE.md` bridge, put the shared policy in `AGENTS.md` and preserve or repair the existing bridge. If the project maintains independent instruction files, keep their terminology obligations consistent through a shared reference. Use the exact filenames supported by the project; a similarly spelled file does not establish that any harness will load it. For another harness, follow its configured instruction entry point and verify that it references the policy. Do not promise universal loading or invent hooks.

The standing rule must specify reading at task start, English-first contextual usage, correction of confirmed in-scope problems when encountered, and preservation boundaries. If ongoing glossary and anti-pattern maintenance was requested, explicitly authorize those updates and name `curate-terminology`; otherwise name only `use-terminology` and leave reusable record changes to a later curation request. Do not convert a lookup request into standing write authority.

An explicit standing instruction is continuing authorization within its stated scope. It must not recreate situational triggers for unrelated planning, model changes, publication, or repository-wide audits. Later task restrictions, including read-only review, still apply. A pointer in prose is a project instruction, not a deterministic enforcement mechanism.

Check that every referenced file exists, each configured instruction entry point reaches the canonical policy, and the rule does not contradict the user's requested scope. Describe the configured path accurately; static inspection does not prove future runtime compliance. `gigio-project-setup` owns broader project setup when requested, while this skill owns the terminology portion.
