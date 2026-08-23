# Game QA Agent

## 프로젝트 소개

`Sweet Crunch`의 레벨 데이터와 플레이 흐름을 반복 검사하고, 같은 오류를 다시 실행할 수 있는 근거와 한국어 보고서를 만드는 게임 개발용 QA 도구입니다.

![Sweet Crunch 실제 Browser 검사 화면](https://raw.githubusercontent.com/aile1492/game-qa-agent/main/docs/images/browser-smoke-level-1-seed-1492.png)

## 해결하려고 한 문제

무작위 보드를 사용하는 Match-3 게임은 같은 레벨에서도 상태가 달라져 오류를 다시 만들기 어렵습니다. 레벨이 늘어나면 데이터 검사, 여러 Seed 실행, Browser 확인, 관련 코드 검색과 보고서 작성도 반복 작업이 됩니다.

이 프로젝트는 다음 작업을 하나의 요청으로 조정합니다.

- 100개 레벨의 이동 수, 목표, 장애물과 문서 일관성 검사
- 같은 Level·Seed의 초기 보드와 실행 결과 재현
- 전체 Run Trace 저장과 Replay 검증
- 실제 `GameScene`에서 한 번의 Swap과 Cascade 완료 확인
- 문제와 관련된 코드 파일과 줄 검색
- 검증 수치와 해석을 분리한 한국어 보고서 작성

## 설계 판단

LLM에게 게임 규칙의 정답을 맡기지 않았습니다. 계산 가능한 사실은 결정적 코드가 판정하고, 에이전트는 어떤 도구를 어떤 순서로 실행할지 조정합니다.

기본 모드는 API Key 없이 동작해 CI와 회귀 검사에서 같은 순서를 실행합니다. 선택적인 LLM 조사 모드는 OpenAI Function Calling으로 같은 Tool을 호출하지만, 최종 수치는 Tool 출력에서만 생성합니다.

## 실제 해결 사례

검사기가 Sweet Crunch README의 500개 레벨 표기와 실제 100개 레벨의 불일치를 찾았습니다. 관련 파일을 확인해 README를 수정했고, 과거 오류는 Benchmark 사례로 보존해 같은 문제가 다시 생기면 탐지하도록 했습니다.

## 검증 결과

| 검증 | 결과 |
|---|---:|
| Game QA Agent 자동 검사 | 15개 통과 |
| 개발용 오류 Benchmark | 16개 사례, Precision 100%, Recall 100% |
| 시작 상태 감사 | 10,000개, 문제 0건, 재현율 100% |
| 전체 Run과 Replay | 각 1,000개, Replay 성공률 100% |
| 실제 Browser Action | 시작·행동 후 Hash 일치, Error 0건 |
| 사용자 조작 단계 | 8회 → 1회, 87.5% 감소 |

Benchmark 결과는 구현자가 구성한 16개 개발 사례에 한정됩니다. 87.5%는 시간 절감률이 아니라 사용자 조작 단계 감소율입니다.

## 현재 제한

- Simulator에는 특수 젬 5종과 조합 규칙이 아직 없습니다.
- Browser 검증은 한 Action Smoke Test 범위입니다.
- 실제 OpenAI API 통합은 수행하지 않았고 Fake Client 계약을 검사했습니다.
- 사람 대상 수동 QA 시간 비교는 아직 측정하지 않았습니다.

## 사용 기술과 링크

- **사용 기술:** TypeScript, Playwright, Seeded PRNG, OpenAI Responses API Function Calling, GitHub Actions
- [Notion 상세 사례](https://aile1492.notion.site/Game-QA-Agent-QA-3c513eca658781709d09e16b1645dbf1)
- [GitHub 저장소](https://github.com/aile1492/game-qa-agent)
- [GitHub Actions](https://github.com/aile1492/game-qa-agent/actions/workflows/qa.yml)
- [시험 대상 Sweet Crunch](https://github.com/aile1492/sweet-crunch)
