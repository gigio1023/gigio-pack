---
name: share-internal-doc
description: >
  Use only when the user asks for a document that colleagues will read without
  this session's context: a shared report, handbook, onboarding page, research
  write-up, decision or status memo, a Notion page, a shareable HTML file, or a
  shared copy of an existing document (사내 공유 문서, 리포트, 핸드북, 온보딩
  문서, 조사 보고서, 결정 메모, 공유본, 노션에 올릴 문서), or names
  share-internal-doc. Shapes the document around one reader, keeps every claim
  traceable to a source a colleague can open, states what the records cannot
  show, runs a sharing pass before anything leaves the machine, and hands
  prose, Korean, figures, and Notion styling to the skills that own them. NOT
  for chat answers, plan files (gigio-write-plan), next-session prompts
  (session-handoff), PR or commit copy, external client deliverables, or prose
  polish alone (slop-aware-writing). Never activate because a conversation
  produced findings worth sharing or because an answer ran long.
---

# Share Internal Doc

Produce a document that leaves this session and works for a colleague who has none of its context. Code leaves a session as a pull request; research, analysis, and decisions leave it as a document, and this skill owns that exit. The author's bar: a document that needs the conversation, another document, or in-house abbreviations to be understood is garbage. Accurate and candid content, low reading effort, and visual finish hold at once; trading one for another is the failure this skill exists to catch.

## Reader brief

Settle these from the request and the material; ask only when an answer would change the document and cannot be inferred.

- The primary reader and the one thing they must understand, decide, or do. Secondary readers get an accessible entry point (summary, first figures) while the body keeps engineering depth.
- Distribution: author only, team, whole company, or outside. Outside is another skill's job. Distribution decides the sharing pass and the link policy.
- Posture. A reader deciding where to stand gets direction first (company, team, their own work, what they can own). A reader learning a field gets a primer about the field, not this company's task list. A reader asked to approve gets the recommendation, reasons, risks, and the ask, never a verdict they lack the context to render; the document carries the judgment and the measurements.
- Language: Korean body, English technical term first with a Korean gloss at first use; figures in English when shared, translated against the project glossary rather than literally.
- Weight matches use: a deep reference and a one-page decision aid are both valid. Not every finding needs a document, and a finished document is left alone.

## Shape

Structure follows the document's purpose. The design system (type, color, citation style, figure idiom) stays constant across a set; section names and order do not. One template applied to every document is a recorded failure.

A cold reader must be able to find seven things. They are questions the document answers, not headings it reproduces: a short memo answers several of them in one line (date, decider, sources) and expands abbreviations inline, while a long report gives each its own section. Name them for the document at hand; two documents in a set should not share a table of contents.

1. What this document is: the question it answers, why it exists, its sources, who wrote it, who it is for, and the reading order. Two sentences in a memo, an opening section in a report, plus an introduction of the organization only when the reader may not know it.
2. The summary, stating conclusions rather than topics: a bold paragraph after the date and provenance line in a short document, its own first section in a long one. Headings state the finding, not the subject.
3. Terms: every abbreviation expanded at first mention. A glossary table only when the document leans on more than a handful of names, tiers, status words, or metrics a colleague would not already know.
4. A reading rule, only when findings rest on records: one paragraph saying that an absent Slack, Notion, GitHub, or Linear record means the reader cannot confirm the work from the record, not that nobody did it, and that the two states call for different actions. Said once, here and inside label definitions, never as a qualifier on each sentence.
5. The body, shaped by the format rules below. The alternatives a decision weighed stay visible.
6. Sources and versions: what was consulted, what this supersedes, what remains open, what could not be verified.
7. About this document: how it was produced, update history, which systems its links need, its limits. A footer line in a memo; a closing section in a report.

Patterns for each part, the memo spine for short task documents, and the research-directory header: [references/reader-and-structure.md](references/reader-and-structure.md). [assets/standalone-spine.template.md](assets/standalone-spine.template.md) lists what must be findable; merge, rename, or drop its headings to fit the document rather than filling it as a form.

## Format

The reader knows nothing of the session that produced the document and will not read it linearly. Most readers see the first section, the figures and tables with their captions, and the last section, then stop. Write for that path.

- Structure carries the content. Use nested bullets, tables, callouts, toggles, columns, and whatever else the target medium renders; a paragraph appears where reasoning needs connecting words, not as the default texture. Nested bullets express real hierarchy (a claim, then its condition); a paragraph chopped at sentence boundaries is not structure. Cells stay short; code-level detail collapses.
- Every sentence earns its place. Delete what the reader loses nothing by losing: scope disclaimers that answer a question nobody asked ("X는 이 리포트의 범위가 아니다", "Y는 여기서 고려하지 않는다"), narration of the author's own steps ("A 디렉터리의 B 파일을 확인했다"), filler modifiers, headings restated as sentences, history that does not change the reading. A stated limit stays only when it changes what the reader may conclude or do. Cutting never removes numbers, sources, conditions, exceptions, or uncertainty.
- Every skim stop carries the finding. The summary states conclusions; headings and captions state findings, not subjects; the closing section states what to do or what remains. A point that exists only inside a mid-body paragraph is invisible.
- Flow, not inventory. A list of facts is not an internal document. Each section answers the question the previous one raised, and each paragraph opens with its point and links to the next with the reason. Stacking self-coined phrases and calling the reading the reader's job is the recorded definition of irresponsible writing.
- Short and easy is the measure, not the author's completeness. Depth shows through architecture (a folded matrix, a sources appendix, a dense figure), never through longer paragraphs.

Devices per medium, the sentences that go, and the flow tests: [references/reader-and-structure.md](references/reader-and-structure.md).

## Claims and their support

- Every material claim links to where a colleague can open the original: Slack permalink, Notion page, GitHub blob pinned to a commit, Linear issue, public source. Inside the company, local files may use the vscode scheme; a shared copy allows only links anyone with normal access can open and names no path on the author's machine.
- Status is carried by words and table columns, never bracket tags. Work status uses 완료, 진행 중, 중단, 보관, 미확인. A claim without a source is 미확인, not guessed and not silently dropped. Quoted remarks name the speaker or mark the speaker unknown.
- Confirmed facts, official narrative, plans, proposals, and the author's inferences stay apart in wording and placement. Internal channels rarely record bad news, so the document states the limitations the record leaves implicit, without the word "truth" anywhere in it. Rejected ideas stay marked rejected; other people's proposals are not folded into the author's.
- Absence of a record is an observation bounded by what was searched; where absence is the finding itself (source code, filings, published papers) it stands as fact.
- Comparisons name their conditions: base checkpoint and lineage before any capacity claim; dataset, metric, threat model, and version behind any "state of the art"; results per dimension, never one aggregate score; correlations computed before asserted; no derived number whose method cannot be stated. Vendor self-reports are labeled; unreplicated results are read down.

Vocabularies, the maturity scale for decision-relevant claims, and the link policy by audience: [references/claims-and-sources.md](references/claims-and-sources.md).

## Language and tone

The document is dry: no strong words, no "확인 완료" badges, no imperatives to the reader, no bold for emphasis, no emoji, no em dashes, no arrows in prose. Reducing risk means removing evaluative framing while keeping facts and numbers; stacking qualifiers is the wrong repair and is itself a recorded correction.

Korean follows the fluent-Korean floor: complete sentence components, particles and endings kept, sentences ending in a predicate, table cells as complete sentences. Accepted project terms come from the records `use-terminology` applies, and gaps found while writing go to `curate-terminology`; beyond those records, terminology comes from papers and practitioner usage, not from internal tickets or AI-flavored coinages; the author has named this company's own GitHub, Notion, and Linear text as a source of facts but not of wording. Titles and figure labels are noun phrases; "A가 아니라 B" appears only for a genuine redefinition. Prose quality and slop diagnosis belong to `slop-aware-writing` and Korean completeness to `korean-clarity`; load both when the session has them, and hold the floor yourself otherwise.

## Figures

Insightful figures are mandatory, and a conversion that strips them has failed. Each figure answers one question, carries a numbered caption ("그림 N."), and has its takeaway stated beside it. Comparisons always include the reader's own organization. ELI5 lives inside figure blocks (one familiar analogy plus the literal mapping), never as the register of the whole document. Nothing enters a figure because space was left over; the standard is the restrained diagrams on the OpenAI and Anthropic engineering blogs. Replacing a figure keeps its question while re-verifying its data. SVG, never ASCII art; a figure that reads small in a narrow column is fixed in the SVG, not by widening the page. Figures share the document's color scheme, dark unless the user asked for light: a dark canvas of their own, light ink, one accent lightened for the dark surface, so the same file reads the same on a light Notion page, in a repository, and in the dark HTML. Where the session has them, `technical-diagram` or `mermaid-diagrams` draw diagrams, `data-chart` plots measured data, and `drawio-diagram` produces native files on request; their own defaults are light, so the request to them names the scheme and the tokens, and an output that comes back light is recolored before it enters the document. Without them, write the SVG directly with the document's tokens.

## Medium

Markdown is the canon; HTML is a generated reading layer rebuilt by script, never hand-edited.

| Reader and use | Medium |
| --- | --- |
| Handoff material another agent or session consumes | A directory of per-topic Markdown files |
| Desktop research or analysis report | Single-file HTML, wide layout (about 1180 to 1700 px, sticky table of contents, chart beside text) |
| Document-shaped page for the company | A Notion page written through the Notion MCP with native blocks, or single-file HTML at reading width (about 720 px) in the dark scheme; the `notion-doc` canon (a light template, template classes only, lint clean) when the user asks for it |
| Working notes, dashboards, knowledge bases | Markdown in the repository; a knowledge base is a linked graph, not a numbered report |

Shared HTML opens offline on Windows: fonts embedded, no external scripts or stylesheets, figures inline. Notion pages are edited only through the MCP or plugin, never browser automation, and re-fetched after large replacements because partial writes have happened. Claude Artifacts are a design reference, not the destination.

The color scheme is dark by default for the page and everything in it: dark canvas, light text, grey plus one accent, figures drawn on the same canvas. Light is a separate render made only when the user asks for it or names print, and the page does not follow the reader's operating-system theme unless the user asked for an adaptive page. Notion sets its own theme, which is why figures placed there carry their own dark canvas. Layout numbers, color tokens, and Notion rules: [references/medium-and-figures.md](references/medium-and-figures.md).

## Sharing pass

Before a document leaves the author's machine, and again after any rewrite, run [references/sharing-pass.md](references/sharing-pass.md). It is a required stage because the cost of skipping it lands on the author.

1. Two questions, answered separately: would this embarrass the company, and would this embarrass the person posting it.
2. People: facts keep real names; evaluations of attitude, ability, or workload become structural statements; customer names and ticket numbers stay so the responsible person can act; named colleagues see their passages before wider circulation.
3. Strip credentials, coordinates of confidential data, anonymous-review submissions, reproducible bypass values, personal HR details, named competitor mockery, offensive payloads, the author's positioning or political calculus, and wording that reads as surveillance.
4. Depersonalize: second-person and "about my role" framing become role language; timestamps and tool fingerprints are generalized, not deleted with a hole; session narration moves to a methods appendix in reader language.
5. Removed coordinates go to the security owner separately, never with the document.

Internal-only sharing keeps internal key and system names; the pass then concentrates on claims stated more strongly than the record supports.

## Finish

- Cold read: give the document alone to a fresh-context reader (a subagent with none of this session) with five to ten questions a colleague would ask, plus "what does this assume I already know" and "where does it contradict itself". Fix what fails.
- A large rebuild starts with a short plan for review. Reused material gets its terminology and structure fixed on the way in; the work neither starts from zero nor imports the old wording.
- Report the absolute path of every file written or changed and the URL of every page published. Record verdicts and decisions in the repository document, not only in chat.
- A document in a repository closes with `commit-and-push`; one that needs review, with `draft-pr`.

## Neighbors

| Skill | Owns |
| --- | --- |
| `slop-aware-writing`, `korean-clarity` | Prose, slop diagnosis, voice, Korean completeness (outside the pack; named when installed) |
| `notion-doc` | Notion block vocabulary and the 720 px HTML template (outside the pack) |
| `technical-diagram`, `mermaid-diagrams`, `data-chart`, `drawio-diagram` | Producing the figures (outside the pack; their defaults are light, so each request names the dark scheme) |
| `session-handoff`, `small-model-handoff` | A prompt for the next session or a weaker model; this skill hands work to colleagues |
| `gigio-write-plan` | Plan files under `.plans/` |

## Gotchas

- After the absence-of-record rule, the tempting repair is a qualifier on every sentence. The recorded correction was "just keep it dry": one reading rule up front, conditions inside label definitions, nothing else.
- Cutting prose has repeatedly been misread as cutting depth. A concise document that hides its research reads as "not much was investigated"; the fix is architecture (collapse, nesting, tables), not more paragraphs.
- ELI5 over the whole document was rejected three times; a section template imposed on every document was rejected the day after the author dictated it; a Notion conversion that dropped a report's figures read as personal notes.
- Delegated figures arrive light unless the request names the scheme, and the first documents were rejected as too bright for exactly this reason. Name the scheme and the tokens in every figure request, and check each render on the canvas it will sit on.
