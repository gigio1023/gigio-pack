# Claims and Sources

Use this when reporting observations, work status, measurements, comparisons, or conclusions that depend on records.

## Match the claim to its support

| Kind | Treatment |
| --- | --- |
| Direct observation | State what the inspected source or artifact shows, with its relevant date or version. |
| Source's account | Attribute the claim to its author or owner; distinguish it from independent confirmation. |
| Derived result | Preserve inputs, method, units, and conditions so the calculation can be checked. |
| Interpretation | Identify the observation and reasoning it rests on; keep material alternatives visible. |
| Plan or proposal | Name its status and owner or proposer when known; preserve rejection or supersession. |
| Unresolved fact | State the bounded unknown when it matters; omit irrelevant speculation. |

Inspect the original source behind a consequential claim. Repeated summaries of one original do not provide independent confirmation. A polished artifact or a worker's completion statement does not establish that its reported work succeeded.

Keep preparation, execution, result validation, and operational use distinct. For example, a successful dataset format check does not demonstrate model performance. Observing a configured capability does not establish that an event occurred. Finding code in a repository does not establish that the current system uses it. Use the actual logs, outputs, or records needed for the claim, and distinguish current behavior from historical or proposed behavior.

A proposal can be clearly identified without being classified as a missing fact. Do not fill a document with unverified claims merely to retain every collected item.

## Make status legible

Express status in ordinary wording or a useful table column. The default Korean work vocabulary is 완료, 진행 중, 중단, 보관, and 미확인 when the project has no established vocabulary. Define ambiguous labels where they affect a decision. Avoid bracket badges such as `[FACT]` and `[INFERENCE]` in reader-facing prose.

Use completion words only for the state actually checked. A report can be finished while the underlying research remains incomplete. Do not turn an owner's intention into an assignment or combine another person's proposal with the author's recommendation.

A maturity classification is useful only when it changes a decision. If needed, distinguish established practice, promising but bounded adoption, a research result awaiting broader confirmation, and unresolved disagreement. Explain the basis; do not impose these categories on every claim or infer maturity from publication prestige alone.

## Bound missing records

State which sources, period, and relevant search limits support a negative finding. A missing item in a specific repository revision can establish absence in that revision. It cannot establish absence throughout an organization or field.

When a report depends on organizational records, explain once that a search cannot establish everything discussed or done outside those records. Put the condition into ambiguous labels and retain local qualifications where claims differ. Repeating a blanket uncertainty phrase after every sentence makes the finding harder to understand.

Keep the observation and its consequence separate: inability to verify ownership may call for clarification; confirmed lack of an owner may call for assignment. Do not invent the second from the first.

## Report numbers and comparisons

Preserve units, denominators, populations, periods, versions, and the definition of each metric. Distinguish percentage points from relative percentage changes, attempts from unique cases, and prepared cases from executed cases. State exclusions and failed runs when they change interpretation.

Compare like conditions or explain the differences before drawing a conclusion. In model reports, include the relevant checkpoint and training lineage, dataset, task, metric, and evaluation settings. A best-performing claim is bounded by those conditions.

Show important results by dimension when an aggregate would conceal a meaningful failure or trade-off. A summary number is useful when its calculation and limitations are clear and the relevant breakdown remains available. Compute a relationship before describing it as a measured correlation; do not invent derived metadata such as reading time.

Label vendor self-reports and unreplicated results according to what was checked. Distinguish uncertainty in a result from uncertainty about whether it applies to the reader's setting.

## Keep sources usable

Use the source form the reader can access: an original document or attachment, a stable section reference, a Slack permalink, a Notion page, a Linear issue, a public source, or a code link pinned to a revision. Prefer precise locators over a generic homepage. Include the necessary explanation in the document even when the source is linked.

Personal filesystem paths and private ledger codes are suitable for an author-only working record. They are not working citations in a document sent to colleagues. When access is restricted, provide an approved summary or clearly describe the access limit without disclosing confidential locations.

Keep the checked-at date distinct from an event date or file modification date. Record version relationships where a reader could otherwise use superseded results. Preserve quotations and archived originals; correct current explanation without silently altering the historical record.
