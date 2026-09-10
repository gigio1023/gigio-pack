# Reader and Structure

Load this when deciding how a document opens, how it is sectioned, or how much to cut. Every pattern here came from a correction the author made on a real document; the dates are in [sources.md](sources.md).

## Readers seen so far

| Reader | What they need first | Shape that worked |
| --- | --- | --- |
| A new engineer deciding where to stand | Direction: where the company is going, what the team must become, what they can own | Part 1 judgment (company, team, individual, ownable work), each point backed by two to four linked sources; Part 2 "근거와 세부" holds the findings |
| An engineer learning a field the company works in | A primer about the field, its central papers, and how the state of the art shifted (or a statement that it did not) | Chapters by concept with a role-based reading path at the top ("독자의 질문 | 읽을 장"); the company's own tasks appear as examples, not as the spine |
| A decision maker asked to approve or choose | The recommendation, the reasons, the risks, the ask, and the alternatives that were weighed | Summary paragraph, then reasons of the same kind, then the option table with the chosen option marked and why it was not trivial |
| A colleague picking up a task or a plan | The one product decision, the representative task, the completion artifact | The memo spine below; proposals labeled as proposals |
| Anyone at the company opening a shared HTML file from Notion | Enough to understand it with no other document open | The standalone spine in the skill body plus the glossary and reading rule |

The reader never does the author's judging. A document that asks its reader for section-by-section verdicts on work they have not done was rejected with "판정을 내가 왜 맡아, 맥락도 모른다". Hand over measurements and reproducible assets; state the judgment yourself.

## Summary placement

- Under roughly three screens: a bold paragraph directly after the title, date, and provenance line ("2026-09-09 재검토 · 대상: … · 모델 성능은 원문 보고값이며 이번에 추론을 다시 실행하지 않았다."). No "Executive Summary" heading.
- Longer: a numbered first section ("1. 한 장 요약" or "요약") with the key findings numbered, after the "이 문서와 배경" block.
- In both, headings and figure titles state the finding. "Q3 매출" is a subject; "Q3 매출 23% 증가" is a finding.
- Read the headings alone in order. If they do not tell the story, the structure is wrong.

## Memo spine for short internal task documents

Used for work proposals, task selection, and follow-ups. The author names this style after a personal repository whose writing it imitates. Target about 8 KB.

1. Title.
2. One line with date and decider.
3. Two or three sentences that open with the question the work answers.
4. One mermaid diagram that explains the mechanism at ELI5 level.
5. Background.
6. Why now.
7. What will be built, as one product decision, one representative task, and one completion artifact. Three vague proposals blended together were rejected as "셋다 너무 애매하고 모호하다".
8. The first two weeks, then what follows.
9. When the work touches another team: the first sentence to say to them, as a polite blockquote.
10. Grounds, with links.
11. One line of limits and what was not confirmed.

When the memo proposes work in another team's area, the tone rules are fixed: justification first, tied to the author's actual role and to a company direction document; curiosity, authorship, and GPU appetite are not reasons. State the non-intervention rules (no new access requests, no touching their branch, data, or meetings, deliver once in writing, drop it if there is no response, the decision is theirs). Size the tasks at half a day to two days, at most three, the last one conditional on the other side opening the door. Place it after the first- and second-priority schedule. Phrase the offer as "wrote this, use it if useful", never "I want to own this".

Plans must be executable by the author alone. A step that waits for someone's approval, consultation, or answer is close to disallowed; substitute the closest public option and label the substitution.

## Long report spine

0. 이 문서와 배경: what the document asks, who the organization is, how the investigation was done and its limits, the glossary, and the reading order.
1. 한 장 요약.
2. Numbered chapters, each opening with its finding.
3. 부록: 방법·한계, and where relevant the reconstructed timeline.
4. 이 문서에 대해: generation method, update history, link conditions, limits.

Chapters that classify findings by the kind of record behind them (for example "티켓 없음" versus "죽은 티켓") make the reading rule concrete instead of abstract.

## Research directory header

Every research directory README opens with seven fields: 목적 (the question), 상태 (완료 / 진행 중 / 중단 / 보관 / 미확인), 기준 시점 (the date or revision the facts were checked at, distinct from the file's modification date), 먼저 읽을 자료, 근거 (where the raw material, collection log, corrections, and counter-reviews live), 판본 관계 (what this supersedes and how it differs from later drafts), 다음 작업 (or the statement that none remains).

## Structure over prose, without losing depth

The complaint was never "there is prose"; it was "almost every section is unbroken prose and that is exhausting". The repairs:

| Cut | Keep |
| --- | --- |
| Repetition in a different form (the same fact in prose and again in a table) | Numbers, units, denominators, periods |
| Sentence-shaped labels ("이 절에서는 … 설명한다") | Conditions, exceptions, requirement levels |
| Project history that does not change the reading | Sources and their links, even when trimming hard |
| Narration about how the document was produced ("이전 집계의 오류", "복구했다", "헤드리스") | Uncertainty and what could not be verified |
| Interactive chrome a document does not need (tabs, buttons, badges, tags, emoji in titles) | The alternatives a decision weighed |

Bullets are for parallel items. Nesting expresses real hierarchy (parent claim, child condition). A table cell holds one short statement; long content moves to collapsed detail under the row or to a chapter. Code-level knowledge collapses under toggles so that the mechanism and its figure stay in front. Dividers and whitespace separate sections; header colors help scanning in Notion.

The visible research depth matters. A concise document that reads as "조사 얼마 안했네" fails even when accurate. Depth is shown through architecture: a large comparison matrix folded in as a collapsible chapter, an appendix of sources, figures that carry many data points legibly. It is not shown through longer paragraphs.

## The reading rule paragraph

Place it after the glossary and before findings, in the document's own words. The shape that was accepted:

> 이 문서에서 "티켓이 없다"는 말은 Slack, Notion, Linear 세 곳 어디에도 그 일을 추적하는 항목이 보이지 않는다는 뜻이지, 아무도 그 일을 하지 않는다는 뜻이 아닙니다. 새로 온 사람이 문서로 확인할 방법이 없다는 문제는 티켓을 만들면 풀리고, 실제로 아무도 안 하고 있다는 문제는 담당자를 정해야 풀립니다.

Counts that were taken directly from files and commits are facts and need no such rule; the rule applies to judgments about discussion, agreement, ownership, and response.

## Existing material

Reuse rather than restart: existing research files and reports are valid sources whose terminology, structure, and prose are usually poor. Take the information, not the wording, and record terminology corrections in the project's terminology file instead of rewriting every old document. A finished document that already meets the bar is not polished further; editing intensity follows the document's state, not a uniform pass.

Before any large rebuild, submit a short plan (which documents, which sections, which figures) and wait for the review. Work that ran ahead of that review was halted twice.
