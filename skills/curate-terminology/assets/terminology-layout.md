# Terminology Layout Template

Create these documents in the consuming project when establishing a collection. Replace the illustrative labels with supported entries and real sources; do not publish placeholders as researched findings. `terms.md` is one possible topic filename. Add other topic files only when they have content and add their links to the root index. Reference-record fields are defined in [records and layout](../references/records-and-layout.md).

## Project root: terminology.md

```markdown
# Terminology

Use the English names and contextual meanings recorded here. Detailed definitions and expressions live under `docs/terminology/`; preserve their usage conditions and company-specific scope.

## Representative terms

| Term | Concise meaning and scope | Reference |
| --- | --- | --- |
| Representative term | Supported definition for this project's context | [R001](docs/terminology/references.md#r001) |

## Index

- [Detailed terms](docs/terminology/terms.md)
- [References](docs/terminology/references.md)
```

## Detail document: docs/terminology/terms.md

```markdown
# Detailed Terms

[Terminology index](../../terminology.md) · [References](references.md)

## Detailed term

**Meaning and status:** Supported contextual definition and whether this is industry usage, a source-specific definition, or a confirmed local meaning.

**Use and distinctions:** Conditions, neighboring concepts, and an appropriate example.

**Reference:** [R001](references.md#r001), with the section or page supporting this entry.
```

## Reference document: docs/terminology/references.md

```markdown
# References

[Terminology index](../../terminology.md)

<a id="r001"></a>
## R001 — Source title or decision description

- Author or owner; source kind: supply the actual attribution.
- Source location: canonical URL, DOI, repository path with revision, or dated local decision pointer.
- Version and date checked or confirmed: supply the applicable edition and actual date.
- Supporting passage: section, page, function, or decision location.
- Used by: [Representative terms](../../terminology.md#representative-terms) and [Detailed term](terms.md#detailed-term).
- Inspection status: what was read, limitations, and local original/text/metadata links when available.
```

Only source records belong in the reference document. Keep definitions and corrections in their owning documents. Preserve protected source material and never turn an inaccessible source or an unanswered user question into a verified reference.
