# Merge rationale

super-interview는 기존의 유사한 역할을 하는 skill들을 따로 유지할 때 생기는 drift를 줄이기 위해 만들었다.

통합 포인트는 아래와 같다.

## From OMX
- 구현 전에 먼저 intent, scope, boundary를 분해하는 discipline
- 질문을 위한 질문이 아니라 실행 전 오해 비용을 낮추는 접근
- 불필요한 구현 점프 방지

## From Superpowers brainstorming
- discovery 뒤에 design gate를 두는 구조
- 승인 가능한 설계 spec 하나로 수렴하는 canonical artifact 철학
- 승인 전 구현 금지, 승인 후 planning handoff 고정

## From deep-interview
- ambiguity를 축별로 줄이는 인터뷰 루프
- readiness 판단
- brownfield에서 baseline branch/worktree/artifact를 먼저 확인하고 질문을 anchor하는 규칙
- shorthand 답변 해석, 질문 전제 교정 처리 같은 compact answer-interpretation 규칙
- 필요 시 deep mode, scoring, ontology tracking, challenge modes 사용
- ontology에서 같은 개념은 같은 이름을 재사용하고, 대부분 같은 개념의 rename은 new가 아니라 changed로 취급하는 semantics
- stall rule, fast-path, soft warning, hard cap, early exit 같은 discovery guardrail
- autoresearch 시 mission/evaluator를 먼저 명확히 하는 guidance

## Intentionally excluded from deep-interview
- always-on scoring, ontology 출력, 장황한 progress ceremony
- state persistence/resume 중심 운영을 기본값으로 두는 것
- Hermes 전용 chat alias, resume file, handoff package, JSON schema machinery
- clarified-spec / handoff / transcript 등을 별도 필수 artifact로 강제하는 구조

super-interview는 deep-interview의 질문 품질과 readiness 판단은 가져오되, runtime/state 중심 설계는 기본 흐름에 넣지 않는다.

## Why one skill
- discovery와 design이 분리돼 있으면 handoff friction이 생김
- 여러 skill에 중복 규칙이 퍼지면 관리 비용과 drift가 커짐
- canonical workflow 하나로 합치면 재사용성과 유지보수성이 올라감
- 기본 산출물을 single canonical spec으로 유지해야 downstream plan/implementation handoff도 단순해진다
