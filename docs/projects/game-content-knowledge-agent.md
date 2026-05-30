# Game Content Knowledge Agent

## Summary

Game Content Knowledge Agent는 기존 상용 게임 콘텐츠 구조를 재사용 가능한 knowledge pack으로 정리하고, 사용자가 제공하는 기획서를 바탕으로 안전한 참조를 선택해 구현 초안을 생성하도록 설계한 AI-assisted creation workflow입니다.

이 프로젝트는 GUI나 CLI에서 바로 전체 파일을 자동 생성하는 도구가 아닙니다. 핵심은 AI가 참조할 수 있는 지식 범위, 자동화해도 되는 영역, 수동 통합으로 남겨야 하는 영역을 명확히 나눈 운영 체계입니다.

## Difference From Game Content Automation Factory

두 프로젝트는 목적이 다릅니다.

| Project | Main Role | Key Value |
| --- | --- | --- |
| Game Content Automation Factory | 실행형 생성 자동화 도구 | 기획서, 콘텐츠 이름, 식별자 기반으로 클라이언트/서버 초안, 등록, 검증 흐름 자동화 |
| Game Content Knowledge Agent | knowledge pack 기반 AI 제작 workflow | 안전한 참조 선택, 금지 영역 분리, 수동 통합 범위, evidence 기반 생성 정책 |

## Problem

게임 콘텐츠 제작 자동화에서 가장 위험한 지점은 "생성할 수 있는 것"과 "생성하면 안 되는 것"을 구분하지 않는 것입니다.

특히 다음 영역은 자동화 범위를 엄격히 제한해야 합니다.

- 확률 및 보상 관련 데이터
- 경제 밸런스 관련 데이터
- 운영 환경에 직접 반영되는 통합 코드
- 이미지, 사운드, 애니메이션, 프리팹 등 실제 리소스
- 원본 운영 소스에 대한 직접 수정

Game Content Knowledge Agent는 AI가 이런 영역을 임의로 생성하지 않도록, 지식 참조와 초안 생성 범위를 명확히 제한하는 방향으로 구성했습니다.

## Approach

```text
User design document
  -> read operating rules and workflow docs
  -> inspect knowledge pack
  -> search structural and semantic indexes
  -> select safe references
  -> generate implementation draft
  -> write generation report
  -> list manual integration tasks
```

## Knowledge Pack

재사용 가능한 학습 산출물은 knowledge pack 아래에 정리되어 있습니다.

- structural index
- semantic index
- reverse-design index
- source reference index
- local LLM summaries
- reverse-design briefs
- reports

이 중 local LLM summary는 gold truth가 아니라 advisory context로만 취급합니다. Rule-based facts와 safe source reference를 더 강한 근거로 둡니다.

## Operating Rules

운영 규칙은 AI가 작업할 때 지켜야 하는 경계를 정의합니다.

- 운영 소스는 read-only로 취급
- 확률, 보상, 경제 밸런스 데이터 자동 생성 금지
- 이미지, 사운드, 애니메이션, 프리팹 리소스 자동화 금지
- 통합 단계는 명시적 결정 없이는 수동 통합으로 유지
- 평가 대상 원본을 생성 단계에서 읽지 않는 no-target-read boundary 유지
- knowledge source가 충돌하면 조용히 선택하지 않고 충돌 보고

## Evidence

과거 proof run에는 특정 기존 콘텐츠 원본을 생성 단계에서 읽지 않고도 유사한 구조의 후보를 만들 수 있음을 보여주는 결과가 보관되어 있습니다.

이 evidence는 현재 active workflow가 아니라, knowledge pack 기반 생성 방식의 가능성을 보여주는 historical proof로 취급합니다.

## Portfolio Value

이 프로젝트는 AI Tooling에서 중요한 "생성 능력"보다 "통제 가능한 생성 구조"를 보여줍니다.

- AI가 참조할 수 있는 지식 경계 설계
- 자동화 금지 영역 정의
- source reference와 non-gold summary의 신뢰도 분리
- manual integration boundary 설계
- Agent 세션에서 재사용 가능한 operating prompt와 workflow 문서화

## Resume Summary

Game Content Knowledge Agent는 기존 상용 게임 콘텐츠 구조를 knowledge pack으로 정리하고, AI가 안전한 참조를 선택해 구현 초안을 만들도록 제한한 AI-assisted creation workflow입니다. 확률, 보상, 경제 밸런스 영역은 자동화 금지 범위로 분리하고, 생성 결과에는 참조 근거와 수동 통합 작업을 함께 보고하도록 설계했습니다.
