# Game Content Automation Factory

## Summary

Game Content Automation Factory는 게임 콘텐츠 제작 과정에서 반복되는 데이터 작성, 코드 초안 생성, 등록, 검증 흐름을 자동화하기 위한 AI assisted production tooling 프로젝트입니다.

실무에서 반복 콘텐츠를 제작하며 느낀 병목은 단순히 코드를 작성하는 속도보다, 기획서의 내용을 코드와 데이터 구조에 맞게 해석하고 여러 파일에 일관되게 반영한 뒤 다시 검증하는 과정이었습니다. 이 프로젝트는 그 반복 흐름을 도구화하는 방향으로 설계했습니다.

## Difference From Game Content Knowledge Agent

이 문서는 실행형 생성 자동화 파이프라인을 설명합니다.

Game Content Knowledge Agent는 별도 프로젝트입니다. Knowledge Agent는 실행형 생성기보다 knowledge pack, safe reference selection, manual integration boundary, non-gold summary policy를 중심으로 한 AI-assisted creation workflow입니다.

간단히 구분하면 다음과 같습니다.

- Game Content Automation Factory: 기획서, 콘텐츠 이름, 식별자를 입력해 클라이언트/서버 초안과 등록/검증 흐름을 자동화하는 실행형 도구
- Game Content Knowledge Agent: 기존 구조를 knowledge pack으로 정리하고, AI가 안전한 참조를 골라 초안을 만들도록 제한하는 운영 패키지

## Problem

게임 콘텐츠 제작에는 다음과 같은 반복 작업이 자주 발생합니다.

- 기획서에서 콘텐츠 이름, 식별자, 주요 규칙, 보너스 흐름 파악
- 클라이언트용 설정 데이터와 스크립트 초안 생성
- 서버용 C++ header/source 초안 생성
- 등록 파일 및 설정 파일 갱신
- 누락된 ID, 잘못된 파일명, 등록 누락 검증
- QA와 릴리즈 전 체크리스트 정리

이 작업들은 난이도보다 반복성과 일관성이 중요합니다. 작은 누락도 QA와 릴리즈 일정에 영향을 줄 수 있기 때문에, 사람이 매번 수동으로 처리하기보다 검증 가능한 파이프라인으로 만드는 것이 더 적합하다고 판단했습니다.

## Approach

도구의 목표는 AI가 모든 것을 임의로 만드는 것이 아니라, 사람이 확인 가능한 구조 안에서 반복 작업을 줄이는 것입니다.

```text
Design note
  -> structured input
  -> generation plan
  -> client file draft
  -> server file draft
  -> registration draft
  -> validation report
  -> manual review and integration
```

## Key Features

- 콘텐츠 이름과 식별자 기반 프로젝트 파일 구조 생성
- 클라이언트 설정 데이터 및 JavaScript 초안 생성
- 서버 C++ header/source 초안 생성
- 등록 대상 파일 목록과 체크리스트 생성
- 생성물 검증 리포트 생성
- 사람이 최종 통합하는 manual review boundary 유지

## AI Usage

AI는 다음 영역에서 보조 역할을 합니다.

- 기획서 또는 요구사항 요약
- 반복 코드 초안 생성
- 누락 가능성이 높은 항목 체크리스트화
- 생성물 검증 관점 제안
- 문서화 및 작업 로그 정리

AI가 직접 운영 코드에 반영하는 구조가 아니라, 사람이 검토 가능한 draft와 validation report를 생성하는 방식으로 설계했습니다.

## Portfolio Value

이 프로젝트의 핵심 가치는 "AI로 게임을 만들었다"가 아니라 "게임 개발자가 반복적으로 겪는 제작 병목을 AI Tooling으로 줄이려 했다"는 점입니다.

특히 AI 게임 개발 도구, 내부 생산성 도구, 개발 자동화 엔지니어 포지션에서 다음 역량을 보여줄 수 있습니다.

- 실제 게임 제작 프로세스 이해
- 반복 작업을 구조화하는 능력
- 코드 생성과 검증을 함께 고려하는 태도
- 실무 보안과 공개 범위를 분리하는 판단
- AI를 업무 시스템 안에 제한적으로 통합하는 설계 감각

## Public Disclosure Boundary

이 프로젝트는 실무 도메인과 연결되어 있으므로 공개 범위를 제한합니다.

- 실제 회사 소스 코드 공개 제외
- 민감한 게임 수치, 확률, 보상, 경제 밸런스 관련 정보 공개 제외
- 내부 파일명, 운영 데이터, 배포 정보 공개 제외
- 공개 자료는 설계 의도, sanitized workflow, 포트폴리오 설명 중심으로 구성

## Resume Summary

게임 콘텐츠 제작 과정에서 반복되는 기획서 해석, 데이터 작성, 코드 초안 생성, 등록, 검증 흐름을 자동화하기 위해 Game Content Automation Factory를 설계했습니다. AI가 임의로 운영 코드를 작성하는 방식이 아니라, 사람이 검토 가능한 draft와 validation report를 생성하도록 제한해 실무형 개발 생산성 도구로 구성했습니다.
