# Sharing Pass

Load this before any document leaves the author's machine, and again after a rewrite. The pass exists because the person posting a document carries its cost. Two review rounds in 2026-09 produced the rules below; the second round added the personal axis after the first had cleared the company axis.

## Two questions

1. Would this embarrass the company: customer defects tied to names, unresolved security items, unpublished deals, competitor remarks, confidential coordinates.
2. Would this embarrass the person posting it: personal positioning strategy, political calculus about when to raise a concern, judgments about a colleague's honesty or a paper's transparency, a new hire acting as auditor, methodology that reads as surveillance (counting private messages read, searching channels one is not a member of).

Answer them separately. Clearing one does not clear the other.

## Scope decides the depth

| Distribution | What the pass does |
| --- | --- |
| Author only | Nothing beyond credential hygiene |
| Team | Named colleagues see the passages about them first; risky statements checked; internal key names and system names stay |
| Whole company (Notion, all-hands) | Everything below |
| Outside the company | Another skill; this pass is not sufficient |

For internal sharing the author narrowed an over-eager pass: "사내 공유라 키는 괜찮아. 이런거 말고 서술 내용 자체에 좀 더 집중해서 개선해줘." The substance to tighten was claims whose scope or date was stated more strongly than the record supports (a founding month written as fact when only a quarter was confirmed), and genuine past failures were not to be deleted because they may have been fixed since.

## People

| Keep | Change |
| --- | --- |
| Real names on facts: owner, author, speaker, decision maker | Sentences that read as evaluations of attitude, ability, or workload, rewritten as structural statements ("검토 요청이 한 채널에 몰려 있습니다" rather than "이 팀은 응답이 느립니다") |
| Customer company names and internal ticket numbers, because the person acting on the item needs them | Names of individual customer contacts |
| Unaddressed security items, flagged with a handling notice | Coordinates that would let a reader find the confidential data itself |

Return findings to their original source so the document is not the judge: "지난 분기 보고서는 이 구간을 진단했습니다" rather than "검사한 표본 대부분에 결함이 있었습니다". Where two conventions exist, describe both rather than declaring one wrong. Turn open questions into action guidance ("문의가 오면 원본 문서로 답합니다") instead of doubt.

## Always remove

- Credentials and secrets, including cookies and tokens visible in screenshots; write `[REDACTED]`.
- Coordinates of confidential data: repository names, file paths, Notion page titles, channel names that lead to it.
- Author, role, and result figures of submissions under anonymous review.
- Reproducible bypass values: user-agent strings, system prompt text, OAuth client identifiers, working attack prompts or payloads. Technique family, counts, sources, and judge design may stay; CBRN operational detail never does.
- Personal HR information: probation, employment terms, leave.
- Competitor mockery quoted with the speaker's name.
- Uncensored-model techniques and offensive tooling detail in defensive documents.

## Depersonalize

- Second-person address and "about my role" framing ("<이름>님께 제안된", "<이름>님의 역할은") become role language: "신규 입사자", "AI Engineer".
- Wall-clock timestamps that reveal when the author worked become relative gaps; a sentence naming the specific small models used becomes "소형 오픈 모델을 보조로 물려 두었으므로". Generalize; do not leave a hole.
- Session narration ("복구했다", "헤드리스", "폴백", "빌드 스크립트") moves to a methods appendix written in the reader's language, or goes.
- Statements that assume the conversation ("이번 주", "오늘 푸시", "1차 리포트 대비") become statements verifiable inside the document.
- No path on the author's machine, no `vscode://`, no citation codes from private ledgers.

## Mechanics that held

A build script regenerates the shared copy from the original instead of editing the original: a rules table per report (span rules between two anchors plus literal replacements), a context block inserted at the front (what the document asks, who the organization is, method and limits, glossary, reading order), and a forbidden-token check that fails the build when a personal name, `/Users/`, `vscode://`, an external `<script src>`, or a local relative link survives. Handling notices use inline style only so the document's own stylesheet stays untouched. Removed coordinates are collected in a separate handoff file for the security owner and are never uploaded with the documents.

Publication is staged: private page first, wider circulation after the pass and after named people have seen their passages. If Korean text corrupts during a publish, stop the batch rather than let the page go live.

## After the pass

Re-fetch what was published and diff it against the source; a Notion replacement of 192 items once applied only 100 silently. Report the absolute paths of the shared copies and the URLs of the pages. Keep the originals unchanged.
