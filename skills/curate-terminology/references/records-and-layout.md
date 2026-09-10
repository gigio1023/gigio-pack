# Records and Layout

Use this reference when creating, updating, or splitting terminology documents. These paths are relative to the consuming project's root, not the installed skill directory.

## Root index, detailed documents, and references

Use this default layout for new collections and requested layout migrations:

```text
terminology.md
docs/terminology/
  terms.md
  expressions.md
  internal-names.md
  anti-patterns.md
  references.md
```

`terminology.md` is the entry point: common usage rules, a small set of representative or frequently used terms with concise definitions, and an index linking to the detailed documents and references. Keep those representative definitions useful on their own; do not reduce the root to a bare directory listing. Keep long explanations and domain-specific detail under `docs/terminology/`. Split `terms.md` or `expressions.md` into descriptive topic files as the material grows, and create the internal-name and anti-pattern files when needed. The topic filenames are examples; the root entry point, detail directory, and dedicated `references.md` are the default locations.

Maintain one authoritative full entry per concept. A representative definition in the root can link to deeper explanation in a topic document; update the root summary when the underlying meaning changes. Do not maintain competing full definitions or reassemble the detailed collection into a monolith. Use [the layout template](../assets/terminology-layout.md) when starting the root index, a topic document, and the reference list.

Read the existing root index before any migration. If a project explicitly mandates another layout, follow that instruction and record the mapping. Otherwise, adopt this layout during authorized setup or a requested reorganization, moving active entries with their links and source IDs. Ordinary lookup does not trigger a directory migration, and archived originals retain their locations.

## Always record references

Maintain `docs/terminology/references.md` as the dedicated list of sources. Record every source used to adopt or change a term, expression, anti-pattern, local meaning, or root representative definition in the same task, including the user's confirmation of a company convention. Record sources actually consulted for a terminology decision, including rejected sources when they explain that decision; label their status so listing them does not endorse their wording. A pre-existing record can be reused; do not create duplicates on every application of unchanged wording. This file contains reference records only. Definitions, editorial rules, research notes, and maintenance history belong in their topic documents or existing change records.

Give each reference a stable ID or anchor and retain it across revisions. Each record contains:

- Title or identifying description, author or owning organization, and source kind.
- Canonical URL, DOI, repository path plus revision, or a dated local user-decision pointer, as appropriate.
- Applicable version or edition and the date checked or confirmed.
- The supporting section, page, function, or other locator and which terminology entries it supports.
- What was actually inspected and any access or verification limitation; local original/text/metadata links when acquired.

Cite the reference record directly from each supported entry and retain any claim-specific passage locator. From the root use a link such as `docs/terminology/references.md#r001`; from a document directly under `docs/terminology/` use `references.md#r001`. Markdown reference-link definitions are scoped to a file, so an unexplained `[R001]` in another file does not link to the central record. The ledger is a source map, not proof that every listed claim is true.

For a user-confirmed local meaning or editorial choice, a dated decision record is the source; do not invent a public citation or expose private conversation content. If the source is missing or unread, mark the claim unresolved and the reference status accordingly. Do not manufacture support to fill a mandatory field. Literature binaries and extracted text remain in the project's literature collection; link them from the reference record and existing literature index.

English names should follow actual research and developer usage, including established spelling, capitalization, hyphenation, and abbreviations. Explanations use the project's working language. A Korean explanation is contextual meaning, not a claim to an official translation or a one-to-one mapping across every field. Preserve paper titles, product names, literal quotations, and identifiers.

## What an entry needs

Keep enough information to distinguish the term from its nearest confusing alternative:

| Record | Required meaning |
| --- | --- |
| Term | Accepted English name; contextual explanation; domain and usage status; assumptions and conditions; confusing neighboring concepts; supporting source with a precise location and version |
| Company or internal name | Exact name and aliases; proper name versus local reuse of an industry term; local meaning or referent; organizational/product scope; internal/external wording; contrast with general usage; dated user confirmation or owning source; implementation status tracked separately |
| Accepted expression | Source passage and location; actor, verb, object, collocation or sentence pattern; contextual meaning; adapted example; conditions and limits on reuse |
| Project explanation | Source and scope; problem and intended users; components and responsibilities; interactions and lifecycle; useful explanation pattern without importing unsupported capabilities |
| Expression correction | Problematic sentence or pattern; accurate replacement or writing principle; why the original misleads; applicable audience and scope; supporting source or editorial decision; exceptions for protected literals |
| Unresolved candidate | Observed wording and location; what is uncertain; available support; the source or observation needed to settle it |

An entry can carry more than one status: research usage, developer usage, a named standard, source-specific, internal, or ordinary description. Use the project's existing labels when equivalent. Research usage is not certification, a standard's existence does not establish implementation compliance, and an internal label is not an accepted technical name merely because it is English.

Separate source-backed corrections from user-selected editorial preferences. A preference can prohibit an otherwise legitimate term in reader-facing prose; record the decision's date, scope, reason, and exceptions. Do not convert that preference into a false statement about the field. Avoid a global search-and-replace list: replacing a word cannot repair an incorrect denominator, unsupported causal claim, or unimplemented guarantee.

## Update without losing provenance

Record material changes outside the reference-only file, where the project already keeps corrections or maintenance history: what changed, why, the supporting source or user decision, the affected files, and unresolved items. Keep existing finding IDs stable. Mark an old decision as superseded with a pointer to the current one instead of silently deleting its history. Do not create a per-run log when the existing record is enough.

When splitting documents, move definitions together with citations, maintain useful old anchors or redirects, update inbound links and indexes, and verify that every original entry is accounted for. Check the root index, representative definitions, topic links, and all reference IDs and anchors together, including links back to literature or user-decision records. Preserve collected originals and historical snapshots. If an old generator could overwrite the new canonical files, disable that obsolete write behavior while preserving the historical material and documenting the new edit location. Do not impose a new build system on human-editable Markdown.
