---
name: share-internal-doc
description: >
  Use only when asked to create, revise, or prepare a document for colleagues
  who lack the authoring session's context, or when named. Covers shared
  reports, handbooks, guides, and decision or status memos in any medium.
  NOT for chat answers, plan files (gigio-write-plan), agent handoffs
  (session-handoff), PR or commit copy, external client deliverables, or prose
  polish alone (slop-aware-writing).
---

# Share Internal Doc

Produce a document a colleague can understand, assess, and use without the conversation that produced it. The document carries the author's selection, explanation, and judgment, with enough support for the reader to check them. Accuracy, useful depth, low reading effort, and visual clarity belong together.

Follow the user's current instructions and the project's document conventions before the defaults here. Infer the reader, purpose, distribution, language, medium, and edit scope from the request and existing material. Ask only when a missing answer would materially change the document; continue independent authorized work while it remains open. A request to review calls for findings; a request to rewrite includes completing the rewrite and its relevant checks.

## Start with the reader's question

Make the subject, purpose, and main message clear near the beginning. Reports and decision memos lead with findings or recommendations. Guides introduce the task or concept the reader needs. Provide the background, definitions, and relationships needed to understand that opening; choose their placement for the actual reader.

A colleague should not need to learn private task codes, inspect a repository, or read another report to reconstruct the main argument. Explain unfamiliar terms at first use and use stable names throughout. Links provide verification and deeper reading; they do not replace the explanation. Self-containment does not require repeating an entire reference library.

Choose the content and order for this document. A field primer teaches the field; a project status report explains the project's state. A comparison supports a choice. Keep the design consistent across related documents while allowing their structures to follow their purposes. Keep headings short and informative; place the explanation in the content they introduce.

## Select, connect, and judge

Collecting facts is only part of writing. Explain what the important observations mean, why they support the conclusion, and which alternatives or unresolved issues affect it. Use only relationships supported by the material; a fluent transition must not invent causality, agreement, priority, or certainty.

When asked for a recommendation, make one with its reasons and limitations. Give the reader enough context to exercise their decision authority. Do not hand them unexplained options or ask them to perform the analysis the document was meant to provide. Distinguish the author's recommendation from an approved decision or somebody else's proposal. When the framing is still being discussed, make the argument reviewable before investing in presentation; preserve an explicit request to discuss a draft first.

## Keep claims faithful to their support

Use original records and inspected artifacts for material factual claims. Attribute source reports, plans, proposals, and inferences so their status is clear in ordinary wording or useful table columns. A prepared environment, an executed experiment, a validated result, and an operational deployment are different states.

Preserve numbers, units, denominators, dates, versions, conditions, exceptions, and attribution. Comparisons need comparable conditions or an explicit explanation of their differences. Keep important variation visible when providing a summary number. A citation must support the exact claim, and its target must be usable by the intended reader.

State what a search or observation can establish. When missing records drive conclusions, explain the search boundary once where it affects interpretation. Finding no record does not establish that no work occurred. Keep consequential uncertainty beside the claim; avoid repeating a blanket caveat throughout the document.

## Reduce effort without thinning the work

Remove repetition, generic background, empty transitions, and narration of the drafting process. Preserve the facts and connecting explanation needed to understand the result. Keep limitations that change what the reader may conclude or do.

Use connected prose for reasoning, bullets for parallel items, steps for order-dependent actions, and tables for repeated fields or comparisons. Nest only when the hierarchy carries meaning. A table cell should remain easy to scan; move long explanation beside the table or into linked detail.

Put the important conclusions and their support on the main reading path. Move supporting volume into appendices or expandable detail where the medium allows it. Do not hide a decisive condition there. Let the breadth of sources and analysis remain inspectable without making every reader traverse it.

## Write plainly and precisely

Use a measured, direct voice. State actors, actions, objects, and conditions clearly. Avoid inflated judgments, invented terminology, stock contrasts, and conclusions that merely repeat the opening. Keep useful technical detail and established domain terms.

Apply `use-terminology` and `curate-terminology` for accepted terms, expressions, and scoped corrections. Internal records establish internal facts and names; they are not automatically models of good technical writing. Preserve quotations, identifiers, and original records while correcting the explanation around them.

For Korean documents, the default is Korean explanation with established English technical terms where they aid precision and lookup. Keep necessary particles, predicates, and logical relations. Headings, labels, and table cells can remain phrases when their meaning is complete in context. Use `slop-aware-writing` for prose revision and `korean-clarity` for Korean clarity when available; retain these principles when they are not.

## Explain visually where it matters

Actively look for relationships, mechanisms, comparisons, and changes that a figure would make easier to understand. Preserve the question and useful information in existing figures during revision or conversion. A document that depends on a figure is incomplete when that figure disappears.

Each figure needs understandable labels, a clear reading order, and a caption or adjacent explanation of its takeaway and relevant conditions. Explain unfamiliar ideas at an accessible level where needed; use an analogy only when the literal relationship remains clear. Check legibility in the delivered medium. A short memo may need only a paragraph or table.

## Read the relevant supporting guidance

| Situation | Read |
| --- | --- |
| Choosing structure, depth, or a reading path | [Reader and structure](references/reader-and-structure.md) |
| Reporting findings, sources, status, or comparisons | [Claims and sources](references/claims-and-sources.md) |
| Choosing a medium, rendering, converting, or placing figures | [Medium and figures](references/medium-and-figures.md) |
| Preparing content for its intended recipients | [Sharing pass](references/sharing-pass.md) |
| A recurring writing failure needs a concrete repair | [Editorial examples](references/editorial-examples.md) |
| Maintaining or changing this skill | [Sources and provenance](references/sources.md) |

The [standalone review questions](assets/standalone-spine.template.md) support a cold read; they are not a document outline. Formatting and delivery details belong to the chosen medium. Preserve the established source of truth rather than converting every document to Markdown or HTML.

## Verify and finish the requested work

For a new or substantially restructured document, use an isolated reader when delegation is authorized and available. Give that reader the document and intended audience, without the drafting conversation. Check whether they can explain its main point, reasons, important limits, and relevant next action, and identify hidden assumptions or contradictions. Otherwise perform the same read directly and state any material verification limit. A reader test does not prove factual accuracy.

Check changed claims against their sources. After rendering or conversion, inspect the actual output for missing content, figures, captions, links, and unreadable layout. When publication is requested, retrieve the published result and check that the intended content arrived. Fix material failures and complete the required project checks; repeat checks only for a relevant change or unresolved concern.

Run the sharing pass for the intended audience. Deliver the finished artifact and its path or URL, with only the limitations that affect its use. Preserve original records and unrelated work. Continue through `commit-and-push` or `draft-pr` when the user's request includes those actions. Preparing a document does not itself authorize sending messages, publishing it, or reinstalling skills.
