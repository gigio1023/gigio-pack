# Claims and Sources

Load this when labeling the status of claims, choosing a link policy, or reporting numbers and comparisons. The house vocabularies below are the ones the author's repositories already use; do not invent parallel ones.

## No bracket tags

Status is expressed in the sentence or in a table column, never as an inline tag such as `[FACT]` or `[INFERENCE]`. The author's personal repository rules ban mechanical judgment tags outright. Three accepted forms:

- A framing sentence: "모델 성능은 원문 보고값이며 이번에 추론을 다시 실행하지 않았다."
- A status column in a table, using one of the vocabularies below.
- A definition inside the glossary that carries the condition, so the term itself signals the status.

## Work status (five words)

| Word | Use |
| --- | --- |
| 완료 | Finished, with the result present in the named location. A finished report can still disagree with current facts |
| 진행 중 | Work observed to be moving, with a current draft or branch |
| 중단 | Stopped before completion; say by whom and when if the record shows it |
| 보관 | Kept for reference, superseded or out of scope |
| 미확인 | No source supports a status. The default whenever a claim has no source |

## Maturity of decision-relevant claims (four tiers)

Each tier carries what a reader may do with it, which is what makes it more useful than a flat fact/inference split.

| Tier | Meaning | License |
| --- | --- | --- |
| 확립된 관행 | Repeated across organizations, tools, and standards; failure modes well known | Default design candidate |
| 의미 있는 전환 | Changes how a problem is solved or evaluated, with observed follow-on adoption | Limited comparative experiment and adoption review |
| 연구 선두 | Ahead in a specific paper or benchmark, lacking generalization or independent replication | Exploratory experiment; not a default |
| 합의 없음 | Policies, contexts, or metrics conflict, or the record is thin | Decide requirements and risk tolerance first |

## Terminology authority (six tiers)

학술 (defined in the cited field's literature), 개발 (used by real systems and official documentation), 규격 (fixed by a standard), 출처 한정 (a method or metric defined by one paper or benchmark), 내부 (a name inside this company's products, datasets, code, or proposals), 서술 (a descriptive phrase that is not a method name). Internal names are never presented as standard terms; a project-root terminology file with an anti-pattern companion is the place to record corrections, and project instructions require it.

## Kinds of claim and how each is worded

| Kind | Wording |
| --- | --- |
| Confirmed fact | Stated plainly with its source link and, when time-sensitive, "YYYY-MM-DD 기준" |
| Official narrative | Attributed to the document or announcement that made it; stated as what it claims |
| Plan | Attributed to its owner and date; not described as done |
| Proposal | Labeled 제안, with the proposer named; the author's proposals are not merged with other attendees'; rejected proposals stay marked rejected with the stated reason |
| Author's inference | Introduced as the author's reading, with the observation it rests on |
| Unknown | 미확인, or "확인하지 못한 것" in a closing list; a speaker who cannot be identified is marked unknown |

The word "진실" does not appear in the document even when the job is to surface what the record leaves implicit.

## Confidence decides the wording

Adapted from an external skill (see sources.md) into prose form:

| Support for the exact claim | How it is written |
| --- | --- |
| Original opened and it says this | Stated directly, no strengthening |
| A source says it, not independently checked | Attributed to the source, or the limitation stated |
| Weak or indirect | Not used as central support; at most as a limitation or a lead to verify |
| None | Excluded as fact; the missing source named when the gap matters |

A derived value inherits the confidence of its weakest input. Evaluative words (significant, only, improve, solve, likely) are claims and keep the same rule.

## Absence of a record

Reports built from Slack, Notion, GitHub, and Linear must not turn "no record" into "did not happen". Verbal discussion, direct messages, and meetings leave no trace in those four systems; an earlier version of one report had to correct several counts for exactly this reason. The fix is structural, not per-sentence: one reading-rule paragraph up front, the condition written into the definition of the label ("티켓 없음" means not found in three systems), and a verification step only where an absence becomes a recommendation to act. Absence remains a fact where the record is the thing itself: repository contents, filings, published papers.

## Numbers and comparisons

- Report per dimension (per direction, per stage, per policy); never one aggregate score.
- Distinguish percentage-point change from relative percent change; compare values only when definitions, populations, units, and periods match.
- Compute a correlation before asserting one; "r = 0.10" is honest, "strong relationship" is not.
- Do not attach derived metadata whose method cannot be stated. An estimated reading time was removed for this reason.
- A model comparison opens with the base checkpoint and the training lineage (base, SFT, GRPO or LoRA, deployment) and the evaluation conditions before any capacity claim. Non-equivalent runs are not combined into one table.
- "State of the art" is written only with the dataset, metric, threat model, and version it holds for.
- Vendor figures about the vendor's own product are labeled "제공자 자체 평가". Results without peer review or independent replication are read down to 연구 선두 or 합의 없음.
- When documenting sources rather than paraphrasing them, quote verbatim and record title, full URL, last-modified date, author, and status. Do not summarize a policy sentence.

## Link policy by distribution

| Distribution | Allowed link targets |
| --- | --- |
| Author only | Anything, including `vscode://file/<abs>:<line>` for local files (browsers download `.md` rather than render `file://`) |
| Team or company, internal | Slack permalinks, Notion pages, GitHub blobs pinned to a commit, Linear issues, HF or public pages. No local paths, no `vscode://`, no citation codes from the author's private ledgers |
| Outside the company | Public sources only, and a different skill |

Citation apparatus that has worked: superscript footnotes into a citation register; every code claim linking the exact blob at a pinned commit, never a branch head; Slack permalinks in the workspace's archive format; Notion URLs. Trimming a document never trims this apparatus: "참고한 내용, 레퍼런스는 자세하게 남기는게 맞아".

## Preserve the record, correct in commentary

Quotations, collected originals, recovered snapshots, and past records are preserved as they were. Corrections live in the commentary and in the current report. Dated freshness ("2026-09-08 기준") accompanies any claim that can go stale, and the checked-at date is distinct from a file's modification date.
