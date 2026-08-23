# AI Game Development Portfolio

게임 클라이언트 개발 경험을 바탕으로, AI와 함께 게임을 기획하고 구현한 과정과 게임 제작에서 발견한 반복 업무를 개발 도구로 확장한 경험을 정리한 포트폴리오입니다.

이 저장소는 회사 내부 소스, 실제 운영 데이터, 민감한 게임 수치와 내부 파일명을 공개하지 않습니다. 공개 가능한 개인 프로젝트를 중심으로 문제, 구현 방식, 결과와 검증 근거를 설명합니다.

## 한눈에 보는 경험

- 상용 게임 클라이언트 개발 및 운영 경험 8년
- 슬롯형 게임 콘텐츠 50종 이상 제작
- Cocos Creator, JavaScript, C++, TypeScript 기반 실무 개발
- AI와 협업해 만든 모바일 퍼즐 게임 **Word Bloom** Google Play 출시
- Godot와 Phaser 3를 활용한 퍼즐 게임 제작
- 게임 제작 경험을 QA 자동화, 코드 검색, 자료 조사 도구로 확장

## 대표 프로젝트: Word Bloom

기획부터 구현, 일부 그래픽 제작, 모바일 빌드와 Google Play 출시까지 혼자 진행한 단어 퍼즐 게임입니다.

![Word Bloom 게임 화면](https://raw.githubusercontent.com/aile1492/word-bloom/main/screenshots/02_gameplay.png)

- 단어 퍼즐 규칙과 글자 배치 방식 구현
- 홈, 게임, 일시정지, 결과 화면의 흐름 구성
- 게임 진행 상황과 사용자 설정 저장
- 모바일 화면과 Android 빌드 대응
- ComfyUI를 활용한 일부 그래픽 제작
- AI를 기획, 구현 보조, 코드 검토와 문서화에 활용

[Google Play에서 보기](https://play.google.com/store/apps/details?id=com.wordbloom.game) · [GitHub 저장소 보기](https://github.com/aile1492/word-bloom)

## AI와 함께 만든 게임

### Sweet Crunch

같은 그림의 블록을 3개 이상 연결하는 디저트 테마 퍼즐 게임입니다. 보드 처리, 연쇄 제거, 특수 블록, 장애물과 레벨 데이터 구성을 구현했습니다.

- 사용 기술: TypeScript, Phaser 3
- [GitHub 저장소](https://github.com/aile1492/sweet-crunch)

### 2048 Puzzle

같은 숫자 블록을 합쳐 더 큰 숫자를 만드는 퍼즐 게임입니다. 이동과 합치기 규칙, 여러 게임 모드, 화면 상태 관리와 테스트 가능한 게임 로직 분리를 구현했습니다.

- 사용 기술: Godot, GDScript
- [웹에서 실행](https://aile1492.github.io/2048-puzzle-web) · [GitHub 저장소](https://github.com/aile1492/2048-puzzle)

[게임 프로젝트 상세 설명](docs/projects/supporting-game-projects.md)

## AI 개발 도구

### Game QA Agent

`Sweet Crunch`의 100개 레벨을 대상으로 규칙 검사, Seed 기반 Simulation, 실제 Browser 실행과 코드 근거 검색을 한 요청으로 조정하는 QA 자동화 도구입니다.

- 시작 상태 10,000개 검사, 전체 Run과 Replay 각 1,000개 수행
- 개발용 오류 사례 16개에서 Precision·Recall 100%
- 같은 결과를 유지하면서 사용자 조작 단계를 8회에서 1회로 감소
- 문서의 500개 레벨 표기와 실제 100개 레벨의 불일치를 찾아 수정하고 회귀 검사로 보존
- 사용 기술: TypeScript, Playwright, OpenAI Responses API, GitHub Actions
- [상세 문서](docs/projects/game-qa-agent.md) · [Notion 사례](https://aile1492.notion.site/Game-QA-Agent-QA-3c513eca658781709d09e16b1645dbf1) · [GitHub 저장소](https://github.com/aile1492/game-qa-agent) · [CI 실행 결과](https://github.com/aile1492/game-qa-agent/actions/workflows/qa.yml)

### Code Search Agent

질문과 관련된 코드 파일과 함수를 찾아 코드 근거와 함께 답변하는 검색 도구입니다. 코드를 의미 있는 단위로 나누고, 질문과 가까운 코드를 찾은 뒤 AI가 관련성을 다시 확인합니다.

- 사용 기술: Python, FastAPI, LangGraph, Tree-sitter, ChromaDB, Next.js, TypeScript
- [상세 문서](docs/projects/code-search-agent.md) · [GitHub 저장소](https://github.com/aile1492/code-search-agent)

### AI Research Agent

복잡한 질문을 작은 조사 항목으로 나누고, 웹 검색과 페이지 읽기, 분석과 보고서 작성을 단계적으로 진행하는 조사 보조 도구입니다.

- 사용 기술: Python, FastAPI, LangGraph, LangChain, Tavily, Jina Reader, Next.js, TypeScript
- [상세 문서](docs/projects/ai-research-agent.md) · [실행 화면](https://ai-research-agent-nine-ashy.vercel.app) · [GitHub 저장소](https://github.com/aile1492/ai-research-agent)

### Game Content Automation Factory

기획서 해석, 데이터 작성, 클라이언트와 서버 코드 초안 생성, 등록 파일 확인을 하나의 작업 흐름으로 묶은 게임 콘텐츠 제작 자동화 설계입니다.

- 사용 기술: Python, Tkinter, JavaScript, C++
- [상세 문서](docs/projects/game-content-automation-factory.md)

### Game Content Knowledge Agent

AI가 참고할 수 있는 자료와 자동화하면 안 되는 영역을 구분한 게임 콘텐츠 제작 절차입니다. 확률, 보상, 경제 수치와 실제 리소스는 자동 생성 대상에서 제외합니다.

- [상세 문서](docs/projects/game-content-knowledge-agent.md)

### UE5 Pipeline Health Agent: 보조 프로젝트

Unreal Engine 5 공식 샘플의 설정과 로그를 읽기 전용으로 확인하고 위험 신호를 보고서로 정리한 프로젝트 점검 도구입니다.

![UE5 Pipeline Health Agent 보고서](assets/ue5_stackobot_report_overview.png)

- Epic의 Stack O Bot 공식 샘플 분석
- `AutomationTool ExitCode=1`과 `BUILD FAILED` 탐지
- HTML, Markdown, JSON 보고서 생성
- 자동화 테스트 11개 통과
- Unreal Engine 5는 주력 실무가 아닌 개인 학습·도구 제작 경험

[상세 문서](docs/projects/ue5-pipeline-health-agent.md) · [GitHub 저장소](https://github.com/aile1492/ue5-pipeline-health-agent)

## 사용 기술

- **실무 주력:** C++, JavaScript, TypeScript, Cocos Creator
- **게임 제작:** Godot, GDScript, Phaser 3, ComfyUI
- **AI 개발 도구:** Python, FastAPI, LangGraph, Next.js
- **AI 협업:** Claude, Gemini, Codex
- **개발 환경 분석:** Unreal Engine 5 공식 샘플

## 경험 범위와 공개 원칙

- Word Bloom은 기획부터 Google Play 출시까지 진행한 대표 개인 게임 프로젝트입니다.
- Sweet Crunch와 2048 Puzzle은 AI 협업 게임 제작 경험을 보여주는 개인 프로젝트입니다.
- Unreal Engine 5는 주력 실무 경험이 아니라 공식 샘플을 분석한 보조 프로젝트 경험입니다.
- Python은 주력 실무 언어라기보다 AI 개발 도구를 만들며 활용 범위를 넓힌 언어입니다.
- 회사 내부 소스, 운영 데이터, 확률·보상·경제 수치, 실제 내부 파일명은 공개하지 않습니다.

## 링크

- [Notion 포트폴리오](https://aile1492.notion.site/AI-Game-Development-Portfolio-33413eca6587815c98e5da909b315272)
- [GitHub 프로필](https://github.com/aile1492)
- [이력서용 요약](docs/resume/summary.md)
