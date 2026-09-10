# Sources and Provenance

Where the rules in this skill came from, so a later edit can check whether the reason still holds.

## The author's own corrections

The skill was distilled on 2026-09-09 from the author's agent sessions between 2026-09-02 and 2026-09-09 across Claude Code, Codex CLI, Hermes Agent, and the repositories they touched (OpenCode held no sessions). Eight harvest lanes read every user turn in about 1,900 Claude Code transcripts, 133 user-originated Codex rollouts and 64 Codex memory summaries, 41 Hermes sessions, 45 Claude memory files, and the repository-side conventions. The Korean working record with verbatim quotes, file paths, and timestamps lives outside the published pack in `docs/design/internal-doc-skill/` (gitignored). The counts below are corrections of a produced document, not mentions.

| Rule | First correction | Repeats | Note |
| --- | --- | --- | --- |
| Document self-contained, no session or abbreviation dependency | 2026-09-03 | 8 or more, four harnesses | "이해되는 문서는 쓰레기야" |
| Summary first, structure over prose, depth kept | 2026-09-03 | 6 or more | Over-cutting corrected three times |
| Absence of record is not absence of work | 2026-09-05 | 3, then reinvented in two later reports | One report's counts were corrected for this reason |
| Dry tone, no stacked qualifiers, no badges | 2026-09-05 | 2 | Nine minutes after the absence rule |
| Every claim linked; shared links restricted by audience | 2026-09-03 | 5 or more | 225-link report; local-path ban 2026-09-05 |
| No bracket status tags | Repository rule, 2026-09 | Standing | Status as words or table columns |
| Content decides sections; design system constant | 2026-09-04 | 2 | Reversed the author's own template of the previous day |
| ELI5 only in figures | 2026-09-03 | 3 | |
| Figures mandatory, restrained, English when shared | 2026-09-04 | 6 or more | Blog diagrams named as the standard |
| Sharing pass, two axes | 2026-09-05, 2026-09-06 | 2 rounds | Internal key names kept for internal sharing |
| Notion through MCP only; Markdown canon, HTML generated | 2026-09-04 | 4 | Partial write of 100 of 192 items observed |
| Terminology from the field, not from internal tickets or AI coinages | 2026-09-04 | 5 or more | Company's own text named as slop wording |
| Plan before a large rebuild | 2026-09-04 | 3 | Work halted twice |
| Proposals executable alone; other teams asked for nothing | 2026-09-07 | 4 | |

## External skills consulted

About thirty public skills were cloned and read on 2026-09-09. Nothing was adopted wholesale; the items below name what was taken. Full verdicts are in the local survey record.

| Source | Taken | Left |
| --- | --- | --- |
| millwright-labs/minto-pyramid-skill | The opening question (does the reader accept a judgment or make a decision) and its exceptions; the red flags for a buried point | None |
| tyroneross/pyramid-principle (source-integrity) | Confidence decides the wording; specific locators; "user input" and "company data" are not sources | The six-skill split |
| anthropics/skills doc-coauthoring | Fresh-context reader test with predicted reader questions | The interactive brainstorming procedure |
| lemieux/rfc-skills | Decide then mark for review instead of an open-questions section; define before referencing; tables for reference data, prose for reasons | Line targets and formatting bans |
| glebis/claude-skills tufte-report | Chart discipline: caption or no chart, three colors, no pie or 3D, computed correlations | Fonts, CDN scripts, layout |
| sammcj/agentic-coding storytelling-with-data, html-design-examples | Action titles, grey plus one accent, exploratory versus explanatory, HTML for human attention and wide use of the screen | Narrative frameworks |
| ngmeyer/skills six-pager | Silent-read margin questions as a cheap reader test | The memo format and prose lint |
| rooftop-Owl notion-ao-writing-conventions | Citation-needed markers never removed silently; limitations mandatory; a reader's pushback is a re-check, not a capitulation | Academic framing |
| daymade/claude-code-skills deep-research | Record failed searches; first-party records establish internal facts but not external validation | The eight-phase pipeline |
| heyman333/agent-notion-template-docs (installed) | Named as the neighbor that owns Notion styling | Nothing to take; it is composed with |
| anthropics/skills internal-comms, eli5 | Router plus per-genre files as a structure; a reader-and-result skill can be ten lines | Formats |
| Diátaxis skills (keithpatton, pfeff, github/awesome-copilot) | The compass as a classification aid for handbooks | Quadrant purity for internal reports |

## Neighbors and prior versions

- `slop-aware-writing` (the author's own) absorbed the earlier `engineering-docs`, `dev-doc-style`, `dev-tech-spec-docs`, and `terminology-review` skills in 2026-07. Its `authoring.md` reader-job table and `source-grounding.md` claim map are the generic layer this skill builds on; this skill adds the house vocabularies, the reading rule, the sharing pass, and the medium routing that are specific to internal sharing.
- `korean-clarity` was split out of `slop-aware-writing` on 2026-09-04 at the author's request; both are named where the body is written.
- The pack's `docs/decisions.md` records why a craft skill was admitted into a loop pack.
