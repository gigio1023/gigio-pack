# gigio-pack — 저장소 안내

자기완결 agent skill pack: 프로젝트 의도(PROJECT.md)·계획(.plans/)·실행·검토를 세션/모델/하네스 교체에도 살아남게 만든다.

## 정본 문서

공개 설계 기록은 `docs/` 4건이다. 스킬을 고치기 전에 해당하는 문서를 먼저 본다.

1. `docs/principles.md` — **철학과 6제약(C1~C6).** 모든 규칙은 여기로 소급돼야 한다. 소급되지 않는 규칙은 빼기 후보다.
2. `docs/rule-ledger.md` — **규칙 대장과 노화 정책.** 하중 규칙의 정당화 유형 5종, 실측 우회 규칙의 측정일, 세대 교체 감사 절차, 삭제·압축 기록.
3. `docs/decisions.md` — 방향 전환 이력. 네 필드(계획 → 현실 → 보수적 선택 → 재검토 시점).
4. `docs/prior-art.md` — 조사한 것, 채택한 것, 기각한 것, 보류한 것.

같은 계약의 사람용 요약이 `CONTRIBUTING.md`다 — 규칙을 바꾸면 함께 갱신한다.

**비공개 원본 기록**: 한국어 작업 원본(`docs/design/`, 조사 32건 포함)은 로컬에만 두고 `.gitignore`로 제외한다. 절대경로·비공개 프로젝트명이 들어 있어 공개하지 않는다. 위 4개 문서가 그 내용을 공개 가능한 형태로 정제한 정본이며, 원본이 필요하면 로컬 파일을 직접 읽는다. 원본의 "datum"은 이 팩의 옛 가안명이다.

## 작업 규칙

- **Markdown 일반 문단은 문단당 소스 한 줄로 쓴다.** 80자·100자 같은 고정 폭이나 문장 단위로 수동 줄바꿈하지 않고, 화면 표시에는 편집기의 자동 줄바꿈을 쓴다. 목록 항목의 문단과 Markdown 템플릿에도 적용한다. 문단 경계, 목록 구조, 표, 코드 펜스, HTML, 의도적인 강제 줄바꿈, frontmatter 의미, 리터럴 예제는 보존한다. Markdown에만 적용하며 코드·docstring의 줄 길이 제약은 바꾸지 않는다.
- **스킬 본문은 전부 영문.** `docs/`도 영문(공개 문서). 이 파일과 로컬 설계 논의는 한국어.
- **금지 용어** (실물 업계 용법이 아닌 한): contract, slice, vertical slice, gate, ceremony. evidence는 output/results/log로. acceptance criteria는 허용. 원칙: 새 이름 전에 실물 시스템(CI, CODEOWNERS, 빌드 시스템)의 기존 이름을 찾는다.
- **스킬에 eval 요소를 넣지 않는다** (평가 스크립트·벤치마크는 스킬 페이로드 밖).
- **기계적 출력 서식 규칙(줄 위치·볼드 금지·파서 관용 등)은 스킬에 넣지 않는다** — 린트/도구의 관심사다.
- **사람 가독성 원칙**: 모든 장치는 사람이 읽고 손으로 고칠 수 있는 마크다운. 데몬·훅·워치독·런타임 상태 파일 금지.
- **Contract steps, not cognition steps**: 번호 붙은 단계는 순서·완전성이 정확성에 속하는 곳에만 — 선행 조회, 승인 경계, 필수 산출 단계, 검증, 감사 가능한 파이프라인. 그 외에는 결과·불변조건·중단 조건만 쓰고 경로는 모델에 맡긴다. 어떤 단계를 빼도 정확성·안전성·감사 가능성이 그대로면 뺀다. 스킬 4개 정거장 분할 자체가 "감사 가능한 고정 파이프라인" 사례(정거장 경계 = 승인·검증 지점)라 유지. 규칙별 수명은 `docs/rule-ledger.md`가 정본 — **새 모델 세대 도입 = 감사 이벤트.**
- **커밋은 사용자가 요청할 때만.** PR은 draft로 올리고 간결한 영문으로 쓴다. 저장소 템플릿이 우선이다. 템플릿이 없으면 `Context`, `Changes` 두 절을 쓴다. CI가 증명하지 못한 결과나 CI의 중대한 예외가 있을 때만 `Validation`을 더한다.
- 한 요청에 여러 정거장의 작업이 포함되어 있으면 이미 받은 권한을 유지한다. 각 산출물을 완성한 뒤 요청된 다음 스킬로 진행하며 같은 승인을 다시 묻지 않는다. 검토·수정·게시·정리의 범위는 구분한다. PR 게시만으로 전역 스킬을 재설치하지 않는다.
- **절차를 시작하는 스킬 9개는 명시적 요청을 요구한다.** 코어 4 + `session-handoff` + `write-internal-doc` + `orchestrate-subagents`/`small-model-handoff`/`fable5-model-routing`의 description은 `Use only when …`으로 연다. 작업 규모, 낯선 도메인, 세션 길이 자체는 실행 요청이 아니다.
- **용어 스킬 2개는 매 작업에 항상 적용한다.** [curate-terminology](skills/curate-terminology/SKILL.md)와 [use-terminology](skills/use-terminology/SKILL.md)를 함께 사용한다. 기존 정의와 표현을 적용하고, 작업 중 만나는 관련 오류·새 용어·동사·표현은 조사하고 기록한다. 변화가 없으면 불필요한 조사나 파일 수정을 만들지 않는다. 명시적 read-only 요청과 원문·식별자 보존 범위는 유지한다. 프로젝트 설정 시 이 상시 지침을 연결한다. 새 용어집의 기본 구조는 루트 `terminology.md`의 대표 정의·index, `docs/terminology/`의 상세 문서, 출처만 기록하는 `docs/terminology/references.md`다. 새로 추가하거나 고친 항목은 반드시 출처 기록을 연결한다.
- **나머지 5개는 기존 트리거를 유지한다.** `deep-interview`/`commit-and-push`/`draft-pr`/`git-worktree-setup`은 사용자의 요청에 대응한다. `find-unknowns`는 별도의 상황 기반 발굴 예외다. 근거는 `docs/principles.md`의 "What may open on its own".
- `python-coding-standards`는 요청된 Python 구현·리팩터링·검토 안에서 적용한다. Python 파일의 존재나 크기만으로 새 작업을 시작하지 않는다. Pydantic 전용 모델링은 공식 외부 `pydantic` 스킬을 사용하고, 나머지 Python 규칙은 이 팩에서 직접 작성한다.
- 검증: `npx skills add . --list --full-depth` 가 정확히 17개를 보고해야 한다.

## 팩 구성과 이름 체계

- **17개**: 코어 4 `gigio-project-setup`/`gigio-write-plan`/`gigio-execute-plan`/ `gigio-review-results` + 발굴 2 `find-unknowns`/`deep-interview` + 실행 지원 5 `orchestrate-subagents`/`small-model-handoff`/`git-worktree-setup`/ `fable5-model-routing`/`python-coding-standards` + 내보내기 4 `commit-and-push`/`draft-pr`/`session-handoff`/`write-internal-doc` + 용어 기록·사용 2 `curate-terminology`/`use-terminology`.
- **작명 원칙**: 이름에 목적과 결과가 드러나야 한다. 기준은 agent-skills의 `skills/development/skill-builder/references/skill-naming.md`. 코어 4개만 팩 접두(`gigio-`), 지원 스킬은 평이한 실명. 한국어 오독 필터 적용.
- **개명 계보** (agent-skills 원본명 기준): `unknowns-pass`→`find-unknowns`, `handoff-prompt`→`session-handoff`, `lower-capability-executor-prompt`→ `small-model-handoff`(worker-brief 경유 — "worker"가 하네스 내부 서브에이전트로 오독돼 재개명), `fable5-judgment`→`fable5-model-routing`, `parallel-subagents`→`orchestrate-subagents`(무동사→동사-목적어). 유지 4개(deep-interview, git-worktree-setup, commit-and-push, draft-pr)는 원명이 이미 목적을 담고 있음. 두 인계 스킬은 의도적 대구: `session-handoff`(다음 세션에게) ↔ `small-model-handoff`(더 약한 모델에게).
- **상호 인지 규칙 (전 스킬 적용됨)**: ① 팩 내부 참조는 **무조건부** — "설치돼 있으면" 가정은 하네스 기능에만 쓴다 ② description에 이웃 구분 1줄 ③ 각 스킬이 끝날 때 다음 정거장 스킬을 지목 ④ gigio-execute-plan은 워커 격리에 git-worktree-setup, 마무리에 commit-and-push, 약한 실행자에 small-model-handoff를 이름으로 호출. 팩 밖 크래프트 스킬(agent-skills의 engineering-docs 등)은 워커가 스킬을 상속 못 하므로 리드·단독 경로에서만, 그것도 설치돼 있을 때만 발동한다 — 팩 문서는 이들을 전제하지 않는다.
- **개별 강점 보존 원칙**: 이관 스킬은 본문을 다시 쓰지 않는다 — skill-builder의 "기존 스킬 개선" 규율(스킬당 1–4개 최소 편집)로 상호 연결만 더한다.
- **범위**: 크래프트 6종·메타 5종은 agent-skills 소유다(2026-07-26 축소, 24→13). 당시 남은 13개 중 어느 것도 원복 11개를 참조하지 않았다. 2026-09-10 추가한 용어 스킬 2개는 프로젝트의 정의·표현 결정과 출처 기록을 유지·적용하는 범위이며, 분야별 용어집이나 일반 문체 교정 도구를 제공하지 않는다. 2026-09-09 추가한 `write-internal-doc`는 크래프트가 아니라 출구로 분류한다. README Scope를 그렇게 고쳤다: 독자·척추·양식·주장 상태·살균·매체는 루프의 일(In), 문장·한국어·그림·Notion 외형은 팩 밖 스킬의 일(Out). 이 스킬이 부르는 팩 밖 스킬(slop-aware-writing, korean-clarity, notion-doc, gigio-figures 3종)은 설치돼 있을 때만 발동한다는 조건부 표현을 유지한다. 근거는 `docs/decisions.md`. 규칙의 한국어 원본(수집 보고서 8건, 통합, 스킬 조사)은 `docs/design/internal-doc-skill/`에 있다.
- **Python 범위**: 2026-09-10 사용자가 Python 구현 규칙을 이 팩에 직접 작성하도록 범위를 확장했다. `python-coding-standards`는 타입·enum·모듈·검증 규칙을 소유하고 Pydantic 전용 가이드는 공식 외부 스킬에 연결한다. 외부 설치는 선택 사항이며, 없으면 검토한 upstream 파일을 읽고 문서로 대체할 수 있다. 전역 설치는 PR 게시 범위에 포함되지 않는다.

## 현재 상태와 다음 작업

- 코어 4개 저작 완료, 잔류 9개 상호 연결 패스 적용 완료, 이중 리뷰 반영 완료.
- 2026-09-09: `write-internal-doc` 추가. 사용자 세션 정정 이력에서 규칙을 수집해 저작. 시험 적용 전. 다섯 편의 공유 문서를 만든 뒤 팩 잔류 여부를 재검토한다.
- 공개 저장소 `gigio1023/gigio-pack`. 설치는 사본 복사 — **스킬을 수정하면 README의 Install 명령을 재실행해야 전역에 반영된다.**
- **다음: 시험 적용 2건.** 관찰 대상 넷 — 병렬 쓰기 이득, 계획 파일의 워커 간 인계 충분성, 리드가 명백히 필요 없어 한 단계(빼기 후보) 실측, 그리고 일반 코드 작업 밖에서 `acceptance` 필드가 실제로 무엇으로 채워지는가. **둘 중 하나는 비엔지니어링 성격으로 잡는다** — 실험 케이스(작업 단위가 파일이 아니라 run, 음성 결과가 산출물)를 추측이 아니라 실측으로 가져오기 위해서다. **시험 통과 전에는 어떤 문서에도 "완료"라고 쓰지 않는다.**
- 통과 후: 전역 AGENTS.md "own the plan" 문단 교체 + Cursor rule 재동기화.
