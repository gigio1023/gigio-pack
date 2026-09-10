# Records and Layout

Use this reference when creating, updating, or splitting terminology documents. Preserve the project's established structure when it already supports retrieval and maintenance.

## Separate reader jobs

A useful larger collection has a short root entry point for mandatory usage rules, classification, and navigation; topic documents for definitions; an internal-name map; an anti-pattern document for recurring expression errors; and source plus maintenance records. These are roles, not a mandatory list of filenames. Start smaller when the scope is small. Do not scatter one definition across several authoritative files or assemble the collection into a monolith after splitting it.

English names should follow actual research and developer usage, including established spelling, capitalization, hyphenation, and abbreviations. Explanations use the project's working language. A Korean explanation is contextual meaning, not a claim to an official translation or a one-to-one mapping across every field. Preserve paper titles, product names, literal quotations, and identifiers.

## What an entry needs

Keep enough information to distinguish the term from its nearest confusing alternative:

| Record | Required meaning |
| --- | --- |
| Term | Accepted English name; contextual explanation; domain and usage status; assumptions and conditions; confusing neighboring concepts; supporting source with a precise location and version |
| Internal name | Exact identifier; owning system and revision; what it actually does; reader-facing explanation; limits on mapping it to a general concept |
| Accepted expression | Source passage and location; actor, verb, object, collocation or sentence pattern; contextual meaning; adapted example; conditions and limits on reuse |
| Project explanation | Source and scope; problem and intended users; components and responsibilities; interactions and lifecycle; useful explanation pattern without importing unsupported capabilities |
| Expression correction | Problematic sentence or pattern; accurate replacement or writing principle; why the original misleads; applicable audience and scope; supporting source or editorial decision; exceptions for protected literals |
| Unresolved candidate | Observed wording and location; what is uncertain; available support; the source or observation needed to settle it |

An entry can carry more than one status: research usage, developer usage, a named standard, source-specific, internal, or ordinary description. Use the project's existing labels when equivalent. Research usage is not certification, a standard's existence does not establish implementation compliance, and an internal label is not an accepted technical name merely because it is English.

Separate source-backed corrections from user-selected editorial preferences. A preference can prohibit an otherwise legitimate term in reader-facing prose; record the decision's date, scope, reason, and exceptions. Do not convert that preference into a false statement about the field. Avoid a global search-and-replace list: replacing a word cannot repair an incorrect denominator, unsupported causal claim, or unimplemented guarantee.

## Update without losing provenance

Record material changes where the project already keeps corrections or maintenance history: what changed, why, the supporting source or user decision, the affected files, and unresolved items. Keep existing finding IDs stable. Mark an old decision as superseded with a pointer to the current one instead of silently deleting its history. Do not create a per-run log when the existing record is enough.

When splitting documents, move definitions together with citations, maintain useful old anchors or redirects, update inbound links and indexes, and verify that every original entry is accounted for. Preserve collected originals and historical snapshots. If an old generator could overwrite the new canonical files, disable that obsolete write behavior while preserving the historical material and documenting the new edit location. Do not impose a new build system on human-editable Markdown.
