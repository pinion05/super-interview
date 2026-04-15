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
- 필요 시 deep mode, scoring, ontology tracking, challenge mode 사용

## Why one skill
- discovery와 design이 분리돼 있으면 handoff friction이 생김
- 여러 skill에 중복 규칙이 퍼지면 관리 비용과 drift가 커짐
- canonical workflow 하나로 합치면 재사용성과 유지보수성이 올라감
