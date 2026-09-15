# Editorial Examples

Use these examples when a draft shows the corresponding reader problem. They illustrate recurring corrections; they are not quotations from private documents or a checklist to impose on every page.

## Context hidden in the session

Weak: “The second option fixes the issue described earlier.”

Repair: identify the option, the actual problem, and why the option addresses it. Include the distinction needed to understand the conclusion in the document; link supporting detail afterward.

Check whether someone who has never seen the conversation can explain the choice without guessing what “second” or “earlier” means.

## Concision that removes the explanation

Weak: a rich comparison becomes “Option A is recommended,” with no trade-off or supporting condition.

Repair: retain the decisive comparison and why it matters. Put the full matrix or methods in accessible detail. Remove repeated prose around the matrix rather than deleting its supporting information.

The reader should see both the recommendation and the condition under which another option would be preferable.

## A fact inventory presented as analysis

Weak: a sequence of source summaries ends with a recommendation that none of the sections explains.

Repair: group observations around the reader's question and show the supported relation between the observations and the recommendation. Attribute interpretation and keep contrary observations when they could change the conclusion.

A transition such as “therefore” cannot supply a missing reason. If the material does not establish the connection, investigate it or state the uncertainty.

## A template overriding the subject

Weak: an organization history, a field primer, and an operating guide all contain the same input–processing–output sections.

Repair: retain the shared design conventions and choose each document's structure for its purpose. A mechanism diagram may suit the guide; a timeline or concept comparison may suit the other documents.

Do not replace forced sameness with forced difference. Reuse a structure when the reader's job actually repeats.

## Missing records and defensive wording

Weak: “No issue exists, so nobody is responsible.” A later rewrite adds “possibly,” “unconfirmed,” and a confirmation badge to every sentence.

Repair: describe the actual observation plainly, such as a missing ownership entry in the named tracker. Keep the search boundary or a specific limitation where it affects the recommended action. Do not replace repeated qualifiers with a mandatory paragraph explaining that records can be incomplete.

The report should distinguish a tracking gap from confirmed absence of ownership without making every sentence a disclaimer.

## Accurate explanations that do not help the reader

The following are generalized editorial examples, not source quotations. The question is whether the information belongs, not how to make every sentence sound shorter.

| Weak reader-facing text | Repair |
| --- | --- |
| “This report reads a fixed snapshot and does not automatically update later execution status.” | Delete the paragraph in an ordinary dated report. If freshness matters, use a source-date label; keep a stale-data warning only where a current action depends on it. |
| “Items whose completion could not be confirmed are distinguished from items that actually stopped.” | Make the status values accurate, for example “Completion log unavailable” versus “Stopped.” Explain the difference only if this reader needs it to act. |
| “Click a point or bar to pin the model and execution settings. Numbered squares list overlapping results.” | Remove the UI tour from the report. Prefer an evident selection panel and a clear overlap label, or simplify the marks; keep necessary unfamiliar help beside the control. |
| “Captions explain the fixed comparison; after filtering, current row counts appear above each chart.” | Remove the narration. Make filter state and counts visible where relevant, and ensure captions describe the displayed results or a visibly separate fixed view. |
| “Latency means the time between sending a request and receiving its response.” | Delete it for an audience already using that term. Define a nonstandard timing boundary if it changes the comparison. |
| “This carefully validated, comprehensive report provides an intuitive overview.” | Delete without replacement. State the actual finding and its support. |

Counterexample: “Timeouts are excluded from the latency median; the failure rate includes them.” Keep this beside the comparison when it changes how a lower median should be interpreted. Removing defensive prose must not hide a denominator change.

## A report disguised as a dashboard

Weak: equal-weight cards repeat a headline count, a large scatter plot occupies the opening because two numeric columns were available, and a sortable full-data table leaves the reader to discover the result.

Repair: identify the question, state the supported finding, and select the comparison that explains it. Put the decisive view first, give related detail less emphasis, and remove panels that add no new relationship. Keep row-level records available when needed for verification or exploration. An exploratory request may need controls, but their initial state should make a useful question visible.

Do not replace a crowded dashboard with an unsupported slogan. The figure, necessary comparison conditions, and reason for the interpretation still do the explanatory work.

## Status stronger than the result

Weak: “Evaluation is complete” when only input files and their schema were checked.

Repair: state which preparation or validation finished and whether model execution and result checking occurred. Keep the actual output or log as support.

The same distinction applies to a configured destination versus a completed transfer, a successful request versus a complete published page, and restored availability versus restored trust.

## Tables and figures that only look structured

Weak: long paragraphs are split into bullets or packed into cells; a diagram adds disconnected boxes and unexplained acronyms.

Repair: use a shared comparison dimension, a real parent–child relationship, or an explicit sequence. Keep cells short and move their reasoning nearby. Give the figure understandable labels, a reading order, and a takeaway.

Judge the result at its delivered size. More nodes, colors, or table rows do not establish more insight.

## Personal working notes sent as a report

Weak: the report describes what the author checked on their laptop and sends colleagues to a personal path.

Repair: explain the relevant system or role, state the finding, and cite an accessible original. Preserve an event time or system identifier when it is necessary to interpret the result. Remove incidental work habits and private positioning.

Check both directions: the shared document should not expose irrelevant private context, and the removal should not erase responsibility, source traceability, or a material limitation.

## Mechanical language repair

Weak: a Korean table cell becomes longer solely to end in a full sentence, or an established English term is replaced with an obscure translation.

Repair: keep a clear label or value when the row and column provide its meaning. Restore a particle, predicate, actor, or condition only where the relation is otherwise ambiguous. Use established terminology that fits the actual field.

Ordinary concise language is the goal. Neither a word blacklist nor uniformly formal sentences can establish clarity.
