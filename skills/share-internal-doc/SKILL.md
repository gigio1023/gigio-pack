---
name: share-internal-doc
description: >
  Use only when asked to create or revise a document colleagues will read
  without the authoring session's context, in any medium, or when named.
  NOT for chat answers, plan files (gigio-write-plan), agent handoffs
  (session-handoff), PR or commit copy, external client deliverables, or prose
  polish alone (slop-aware-writing).
---

# Share Internal Doc

Produce a document a colleague can understand, assess, and use without the conversation that produced it. Include the author's selection, explanation, and judgment, with enough support for the reader to check them.

Follow current user instructions and project conventions before these defaults. Infer the reader, purpose, distribution, language, medium, and edit scope from the request and existing material. Ask only about consequential gaps, continuing work that does not depend on the answer. Review requests call for findings; rewrite requests include the rewrite and relevant checks. Preserve an explicit request to discuss the framing before producing a finished document.

## Principles for every medium

Make the subject and main message clear near the beginning: findings or recommendations for a report, the task or concept for a guide. Supply only the background, definitions, and relationships this audience needs to follow it; self-containment does not require explaining familiar terms or how to read an ordinary document. Links support verification and deeper reading; they must not make the reader reconstruct the argument elsewhere. Let purpose determine structure, reusing a suitable design without imposing one outline on unrelated documents.

Explain why the selected observations support the conclusion. When asked for a recommendation, provide one with reasons, alternatives, and limits that could change the choice; do not return unexplained options for the reader to analyze. Distinguish the author's judgment from an approved decision or another person's proposal. Fluent transitions must not invent causality, agreement, priority, or certainty.

Ground material factual claims in inspected sources. Preserve the attribution, numbers, units, denominators, dates, versions, conditions, and exceptions needed to interpret the selected claims. Preparation, execution, validation, and operational use are different states; reflect the correct state in the result rather than teaching that distinction in every report. Use plain wording or useful status columns, not confirmation badges. A missing record does not prove that work never happened. Bound a consequential negative finding at the affected claim or status label; do not insert a generic reading-rule paragraph. Citations must support the exact claim and be usable by the reader.

Reduce reading effort without thinning the work. Keep a passage when it supplies necessary understanding, supports a conclusion, changes a decision, or enables an action. Otherwise delete it, even if it is accurate: defensive caveats, routine definitions, drafting narration, UI tours, and claims about the document's own rigor often fail this test. Do not turn every deletion into a footnote or appendix. Keep decisive conditions and important variation on the main reading path; genuinely useful supporting detail can remain accessible. Use prose for reasoning, lists for parallel items, steps for order-dependent actions, and tables for repeated fields. Short headings and table cells need not become full sentences when their meaning is clear.

Write directly, with clear actors, actions, and conditions, stable names, and established field language. Apply `use-terminology` and `curate-terminology`; internal records establish internal facts and names, not necessarily good wording. Preserve quotations and identifiers. For Korean documents, use Korean explanation with established English technical terms where useful, keeping necessary particles and logical relations. Use `slop-aware-writing` for prose revision and `korean-clarity` for Korean clarity when available; these principles also apply without them.

Select figures around the reader's question, not the available columns or the desire to fill a dashboard. Make the important comparison visible without requiring filters or clicks to discover the point. Give it more visual emphasis than supporting detail; remove redundant charts, metric cards, and decorative controls. Use readable labels and place the finding and its material conditions where they help, without repeating them in a title, caption, and adjacent paragraph. Preserve useful figures during revision and conversion, and use analogies only when their literal mapping remains clear. A short memo may need no figure. Where styling is controlled, default screen documents and figures to dark; respect requested light, print, and destination-controlled themes.

Match content and attribution to the recipients. Remove credentials, unnecessary private information, and incidental authoring context without erasing relevant failures, responsibility, chronology, or technical conditions. Preserve actual passage-review requirements and reviews already completed. Keep original records and unrelated work intact, and use the project's established source of truth rather than creating a competing editable copy.

## Read for the decision at hand

The principles above cover routine edits. Read a reference when its condition applies, not the whole package for every document.

| When | Read to resolve |
| --- | --- |
| Creating or restructuring a substantial document, or serving readers with different expertise | [Reader and structure](references/reader-and-structure.md): opening, argument, depth, and reusable document forms |
| Handling incomplete or conflicting records, disputed status, or quantitative comparisons | [Claims and sources](references/claims-and-sources.md): attribution, search limits, metrics, and source access |
| Choosing or changing the delivery format, rendering, converting, or producing figures | [Medium and figures](references/medium-and-figures.md): source workflow, appearance, production tools, and destination checks |
| Handling sensitive content, personal attribution, or a changed distribution | [Sharing pass](references/sharing-pass.md): permitted detail, accountability, and required review |
| A draft contains defensive explanations, excessive definitions, UI narration, or other known reader problems | [Editorial examples](references/editorial-examples.md): what to delete, move into the interface, or retain |
| A new or substantially restructured document needs a cold read | [Reader review](references/reader-review.md): questions for detecting hidden context, not an outline to fill |
| Maintaining this skill | [Sources and provenance](references/sources.md): correction history, rule scope, and prompting sources |

## Verify and finish the requested work

For a new or substantially restructured document, check comprehension from the document alone. Use an isolated reader when delegation is authorized and available; otherwise perform the read directly. Supply the document and intended audience, not the drafting conversation. A reader test does not prove factual accuracy.

Check changed claims against sources and the finished copy for recipient suitability. After rendering or conversion, inspect the actual output for missing content, figures, captions, links, and unreadable layout. For authorized publication, retrieve the result and check the changed content for complete delivery. Fix material failures and run required project checks; repeat only for a relevant change or unresolved concern.

Finish with the requested artifact or findings, its path or URL when applicable, and limitations that affect its use. State material verification results briefly; do not praise the document, advertise its completeness, or narrate every check. Continue through `commit-and-push` or `draft-pr` when requested. Document preparation alone does not authorize contacting people, sending messages, or publishing; reuse existing grants rather than asking again.
