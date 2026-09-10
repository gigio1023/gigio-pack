# Source Verification

Use this reference when a definition, expression, or source record changes. The question is what the source supports in this context, not whether the source contains the same words.

## Match the source to the claim

| Claim | Start with | Preserve |
| --- | --- | --- |
| A standard or normative definition | The issuing body's actual specification | Edition, section, normative versus informative text, and applicability |
| An API or developer concept | Official documentation and relevant implementation | Product or library version, input/output behavior, and exceptions |
| A research concept or method | The defining paper and relevant primary follow-up work | Definition, assumptions, experimental scope, and the authors' usage |
| A company proper name or local meaning | Existing naming records, user confirmation, and the owning project | Exact spelling, referent, local scope, audience, and dated confirmation; separate intended meaning from implementation facts |
| An internal metric or behavior | Owning code, configuration, data specification, or documented decision | Exact identifier, revision, formula, unit, denominator, and implementation status |
| A preferred expression | The user's or project's recorded writing decision | Audience, affected surfaces, reason, and protected literals |

## Choose representative sources before extracting language

Prefer a small, field-relevant set of widely adopted, established projects with accountable maintainers and substantive documentation. For infrastructure engineering, Kubernetes and Helm are examples of the intended source class. Find comparably established sources for the actual field; do not import infrastructure vocabulary into agent research merely because those projects are familiar. Inspect their official concept and architecture documents, developer guides, and maintainer-authored engineering blog posts. Record why each source is representative, using actual adoption, sustained maintenance, ecosystem integration, or independent use; stars, search rank, polished prose, and an official-looking domain alone are insufficient.

For papers, start with influential foundational work and recognized follow-ups: established use as a baseline, independent replication or adoption, and sustained citations in relevant primary work are useful selection signals. Well-known arXiv preprints are welcome; peer review is not a mandatory filter, and an arXiv listing alone proves neither influence nor quality. Read the original paper and its relevant author, lab, or established project blog explanations. Use the blog for intuition, implementation context, and expression examples, and the paper for formal definitions and claims. Preserve disagreements rather than blending them. When no established source covers the concept, leave it provisional and narrow the claim instead of promoting an obscure paper to authority.

For general industry terminology, use internal reports and secondary summaries only to locate candidates and original sources. Company naming conventions instead follow [company usage](company-usage.md): confirm the few ambiguous local meanings with the user rather than overruling them with an external definition. Known or disclosed AI-generated articles, synthetic tutorials, automated paper summaries, content-farm explainers, and unsupported derivative posts are excluded as authorities for terminology and expression, even when convenient or hosted by a familiar platform. At most, follow their links to an independently inspected primary source; do not reuse their wording. An official source still needs accountable authorship or editorial maintenance and support in the underlying work. Unknown authorship is not proof of AI generation: inspect provenance and substance, and skip material whose reliability cannot be established rather than guessing who wrote it.

**Explicit source exclusions:** do not use projects named `opencodex` or `oh my claude code` (including case and punctuation variants) as terminology or expression sources. This is the user's source-selection policy, recorded 2026-09-10, not a forensic claim that every passage was AI-written. Do not silently reinterpret those names as a different similarly named project. Their copied or rehosted wording remains excluded. If the task is about one of these projects, inspect it only as the object being described; verify the explanatory vocabulary elsewhere. User-selected exclusions take precedence over popularity.

## Discover and read papers with available tools

Actively use available paper tools instead of relying on recalled titles or web snippets. With the Hugging Face CLI, inspect `hf papers --help` and the relevant subcommand help first, then use `hf papers search "<topic>"`, `hf papers info <paper-id>`, and `hf papers read <paper-id>` when supported. See the [official CLI guide](https://huggingface.co/docs/huggingface_hub/guides/cli). Follow the paper's canonical link to confirm the exact version and inspect the original PDF or full text for the definition. Hub rankings, votes, daily lists, and generated summaries are discovery signals, not authority for wording or evidence of scientific consensus.

Search for the paper's title together with its authors or lab to find a related author explanation; follow links from the paper or official repository when possible. Verify ownership before using a blog as a primary explanation. If `hf` is unavailable or its paper commands differ, use the installed equivalent, the Hub website, a scholarly index, or the canonical paper directly. Missing CLI support is a fallback condition, not permission to invent flags, install software, authenticate, or use a paid service.

Read the passage that defines or uses the concept, including its conditions. A search snippet, abstract, citation count, or paper title is insufficient when the disputed detail lives in the method or appendix. For disputed general usage, compare relevant primary sources and record a field-specific difference rather than forcing a universal synonym. For version-sensitive definitions, verify the current applicable source when available; retain the older edition if it is the implementation's target.

Do not infer deployment from a proposal, training from a score, causality from an uncontrolled comparison, or a formal bound from an observed diagnostic. Match the replacement sentence to the available result. Where access is incomplete, record what was inspected and what remains unknown.

## Save reusable literature during curation

Check the project's literature index before downloading. Save newly discovered relevant primary papers as they are found, within the requested research scope, using the existing literature directory and naming rules. Prefer the lawful author, publisher, or institutional copy. Do not bypass access restrictions or copy private materials into a public skill or PR.

For each acquired paper, record the title, authors, year, canonical URL or DOI, version, retrieval date, local file, content hash, and the terms it supports. Verify the response is the expected document rather than an error page. Keep a searchable text extraction and record its method and status. Inspect the relevant passage in the original when extraction loses formulas, tables, or qualifiers. Use an available extractor; if the preferred tool is missing, choose an installed alternative or record the limitation instead of claiming extraction succeeded.

Link the original, extracted text, and metadata from the literature index and any existing field-level source record. Avoid an orphan metadata file whose paper is listed but whose provenance cannot be reached. A metadata-only record is acceptable when the document is inaccessible; label it clearly and do not cite an unread passage as verified. Do not download unrelated papers to meet a count.

Run the project's existing catalog rebuild and verification after adding literature or changing navigation. Keep mutable source collections in the project, outside the replaceable installed skill. This skill provides the curation method, not a preapproved library of domain definitions.
