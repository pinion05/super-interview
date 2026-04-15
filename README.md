<img width="1536" height="1024" alt="ChatGPT Image 2026년 4월 15일 오후 04_26_39" src="https://github.com/user-attachments/assets/b511ebb8-9b33-4cc1-9cc1-4d4e004b9d10" />


# 수퍼-인터뷰

- OMX의 장점: ambiguity를 체계적으로 줄이고 readiness를 판단하는 인터뷰 중심 접근
- Superpowers 의 장점: discovery 뒤에 바로 design gate와 canonical spec으로 수렴하는 흐름

즉, 이 스킬은 “질문만 많이 하는 인터뷰”도 아니고, “곧바로 설계로 점프하는 브레인스토밍”도 아니다.
기본은 가볍게 진행하고, ambiguity와 risk가 높을 때만 더 깊게 파고들어, 결국 구현 전에 승인 가능한 한 장의 spec으로 정리하는 통합 워크플로우다.

## What it does

super-interview는 아래 두 단계를 하나의 흐름으로 합친다.

1. Discovery
- 현재 코드/문서/설정/외부 사실을 먼저 확인
- 자동 확인 가능한 사실은 직접 확인
- 사용자에게는 사실이 아니라 결정만 질문
- 가장 큰 ambiguity axis부터 줄임

2. Design
- readiness에 도달하면 2~3개 접근법 비교
- 추천안을 제시하고 trade-off를 설명
- architecture / boundaries / data flow / error handling / verification까지 담은 design spec 작성
- 사용자가 승인하기 전까지 구현으로 넘어가지 않음

## Hard gate

사용자에게 검토 가능한 설계를 제시하고 승인을 받기 전까지는:
- 구현 스킬을 호출하지 않음
- 코드를 작성하지 않음
- 스캐폴딩이나 실행 가능한 구현 행동을 하지 않음

이 레포의 가장 중요한 규칙이다.

## Repository layout

- `SKILL.md` — canonical skill definition
- `templates/design-spec-template.md` — 작성용 spec 템플릿
- `references/merge-rationale.md` — 왜 이 스킬이 기존 brainstorming/deep-interview를 합쳤는지 설명

## Mode summary

### `--quick`
- 아주 작은 변경이나 이미 상세한 요청
- 최소 질문, 최소 discovery
- 짧은 spec으로 수렴

### `--standard`
- 기본 모드
- 대부분의 기능 추가/변경에 적합
- weakest dimension 중심 탐색

### `--deep`
- 고비용/고복잡도 작업
- ambiguity scoring
- ontology tracking
- readiness gating
- state persistence

## Default output

기본 산출물은 하나다.

- `docs/superpowers/specs/YYYY-MM-DD-<topic>-design.md`

추가 파일은 deep mode이거나, resume/handoff 자동화에 꼭 필요할 때만 만든다.

## Recommended usage

예시:

- `super-interview --quick "로그인 페이지 카피만 수정"`
- `super-interview --standard "기존 결제 플로우에 환불 상태 추적 추가"`
- `super-interview --deep --show-scores "멀티에이전트 기반 작업 승인 파이프라인 재설계"`

## Why this repo exists

기존에는 brainstorming, interview, deep-interview처럼 유사한 목적의 skill이 나뉘어 drift가 생기기 쉬웠다.
super-interview는 그 중복을 줄이고, 아래 원칙으로 하나의 canonical workflow를 제공한다.

- discovery는 생략하지 않되 깊이는 적응적으로 조절
- 질문 단계와 설계 단계를 섞지 않음
- 문서는 가능한 한 한 파일로 유지
- spec 승인 전에는 구현으로 가지 않음
- 승인 후 다음 단계는 `writing-plans` 하나로 고정

## License

MIT
