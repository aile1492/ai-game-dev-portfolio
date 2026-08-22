# UE5 Pipeline Health Agent

## 프로젝트 위치

이 프로젝트는 대표 게임 프로젝트가 아니라, Unreal Engine 5 공식 샘플을 활용해 개발 환경 점검 도구를 만든 **보조 프로젝트**입니다. Unreal Engine 게임 제작 실무 경력을 의미하지 않습니다.

## 한 줄 소개

Unreal Engine 5 프로젝트의 설정, 로그와 콘텐츠 폴더를 읽기 전용으로 확인하고 위험 신호를 보고서로 정리하는 Python 도구입니다.

## 해결하려던 문제

- 긴 로그에서 실제 실패 원인을 찾는 데 시간이 오래 걸립니다.
- 정상 안내 메시지와 중요한 오류를 구분해야 합니다.
- 파일 이름과 프로젝트 설정을 매번 사람이 확인하면 기준이 달라질 수 있습니다.
- 규칙이 지나치게 엄격하면 정상 파일도 문제로 표시될 수 있습니다.

## 동작 과정

```text
UE5 프로젝트 사본
  -> 프로젝트 구조 확인
  -> 설정 확인
  -> 로그 확인
  -> 콘텐츠 파일 확인
  -> 발견 항목과 근거 정리
  -> HTML, Markdown, JSON 보고서 생성
```

## 공식 샘플 검증

- Epic의 Stack O Bot 공식 샘플 분석
- `AutomationTool ExitCode=1`과 `BUILD FAILED` 탐지
- 정상 캐시와 셰이더 안내 메시지가 잘못된 경고로 표시되지 않도록 규칙 조정
- Unreal Engine이 자동 생성하는 폴더와 사용자 지정 접두사 고려
- 자동화 테스트 11개 통과
- 점검 과정에서 원본 프로젝트 파일을 수정하지 않음

## 사용 기술

Python, pytest, JSON, Markdown, HTML, Unreal Engine 5

## 확인 자료

[GitHub 저장소](https://github.com/aile1492/ue5-pipeline-health-agent)
