# AI Game Development Portfolio

게임 클라이언트 개발 경험을 바탕으로 AI Tooling, 개발 자동화, Agent 기반 워크플로우를 실험하고 정리한 포트폴리오입니다.

이 저장소는 회사 내부 소스나 실제 운영 데이터를 공개하지 않습니다. 공개 가능한 범위 안에서 문제 정의, 설계 의도, 자동화 구조, 검증 방식을 정리한 제출용 허브입니다.

## Positioning

저는 Cocos Creator와 JavaScript 기반 상용 게임 콘텐츠 개발과 운영에 참여해왔습니다. 최근에는 C++ 서버 로직, 빌드와 배포 대응, AI를 활용한 반복 작업 자동화까지 관심 영역을 확장하고 있습니다.

AI는 단순 코드 생성 도구가 아니라, 기획서 분석, 코드와 데이터 초안 생성, 검증, 문서화, 리포팅까지 연결되는 개발 생산성 시스템으로 다루고 있습니다.

## Focus Areas

- AI 기반 게임 개발 도구 제작
- 반복 업무 자동화 및 개발 생산성 개선
- AI Agent, Tool-use, Retrieval 기반 개발 워크플로우
- 게임 개발 파이프라인 분석 및 리포팅
- 클라이언트와 서버 흐름을 함께 고려한 콘텐츠 제작 자동화

## Core Projects

### 1. Game Content Automation Factory

게임 콘텐츠 제작 과정에서 반복되는 기획서 해석, 코드 초안 생성, 리소스 등록, 검증 흐름을 자동화하기 위한 내부 생산성 도구 컨셉입니다.

- Type: AI assisted game development tooling
- Stack: Python, Tkinter, structured data generation, JavaScript draft generation, C++ header and source draft generation
- Portfolio value: 실제 게임 콘텐츠 제작 경험에서 나온 반복 업무 병목을 AI Tooling으로 해결하려는 시도
- Public scope: 회사 내부 자산, 운영 데이터, 민감한 게임 수치, 실제 파일명은 공개 범위에서 제외하고 구조와 설계 의도 중심으로 정리

[Case Study](docs/projects/game-content-automation-factory.md)

### 2. Game Content Knowledge Agent

기존 상용 게임 콘텐츠 구조를 재사용 가능한 knowledge pack으로 정리하고, 사용자가 제공하는 기획서를 바탕으로 안전한 참조를 선택해 구현 초안을 생성하도록 설계한 AI-assisted creation workflow입니다.

- Type: knowledge pack based game content creation assistant
- Stack: knowledge pack, structural index, semantic index, reverse-design briefs, source reference index, agent workflow
- Portfolio value: 단순 자동 생성기가 아니라, 참조 선택, 금지 영역 분리, 수동 통합 범위, non-gold summary 정책까지 포함한 안전한 AI 제작 워크플로우
- Public scope: 확률, 보상, 경제 밸런스, 운영 데이터, 원본 소스 경로는 자동화와 공개 범위에서 제외

[Case Study](docs/projects/game-content-knowledge-agent.md)

### 3. UE5 Pipeline Health Agent

Unreal Engine 5 프로젝트의 로그, 설정, 에셋 상태를 읽기 전용으로 분석하고 BuildCookRun, DDC, shader, validation, asset hygiene 신호를 리포트화하는 Python 기반 개발 자동화 도구입니다.

![UE5 Pipeline Health Agent report](assets/ue5_stackobot_report_overview.png)

- Type: UE5 development automation and pipeline health check
- Stack: Python, pytest, JSON, Markdown, HTML report, Unreal Engine 5 sample project
- Evidence: Epic 공식 Stack O Bot 샘플의 실제 editor log 분석
- Result: AutomationTool ExitCode=1 / BUILD FAILED 신호를 critical finding으로 탐지

[Case Study](docs/projects/ue5-pipeline-health-agent.md)

### 4. Code Search Agent

코드베이스를 AST와 벡터 검색 기반으로 탐색하고, LLM을 활용해 코드 근거 중심으로 답변하는 AI 코드 검색 도구입니다.

- Type: AI code search and retrieval workflow
- Stack: Python, FastAPI, LangGraph, Tree-sitter, ChromaDB, sentence-transformers, Next.js, TypeScript
- Portfolio value: 개발자가 코드 맥락을 빠르게 찾을 수 있도록 돕는 개발 생산성 도구

[Case Study](docs/projects/code-search-agent.md)

### 5. AI Research Agent

질문을 하위 질문으로 분해하고, 웹 검색, 페이지 읽기, 분석, 리포트 작성을 단계적으로 수행하는 LangGraph 기반 연구 Agent입니다.

- Type: Agentic research workflow
- Stack: Python, FastAPI, LangGraph, LangChain, Tavily, Jina Reader, Next.js, TypeScript, SSE
- Portfolio value: Agent workflow, 단계별 상태 관리, source based report generation 경험

[Case Study](docs/projects/ai-research-agent.md)

## Supporting Game Projects

개인 게임 프로젝트는 AI 협업, 모바일 출시 준비, 게임 로직 분리, 리소스 제작 흐름을 보조적으로 보여주는 자료입니다.

[Supporting Game Projects](docs/projects/supporting-game-projects.md)

## Job Fit

이 포트폴리오는 특히 다음 유형의 포지션에 맞춰 정리했습니다.

- AI 게임 개발 도구 엔지니어
- 개발 자동화 엔지니어
- Technical Artist 팀과 협업하는 내부 툴 개발자
- AI Agent 기반 개발 워크플로우 구축 담당자
- 게임 개발 생산성 개선 도구 개발자

[Chrono Studio Job Fit](docs/job-fit/chrono-studio.md)

## Honest Scope

- Unreal Engine 5는 실무 주력 경험이 아니라, 공식 샘플 프로젝트를 분석하고 자동화 도구를 만든 개인 포트폴리오 경험입니다.
- Python은 주력 실무 언어라기보다 AI Tooling과 자동화 프로젝트를 통해 활용 범위를 확장한 언어입니다.
- Game Content Automation Factory는 실행형 생성 자동화 도구이고, Game Content Knowledge Agent는 knowledge pack 기반 AI 제작 workflow입니다.
- 두 게임 자동화 프로젝트 모두 실제 업무 병목에서 출발했지만, 공개 자료에는 회사 내부 자산, 운영 데이터, 민감한 게임 수치, 실제 파일명을 포함하지 않습니다.
- AI API key가 필요한 부분은 실제 키 없이 mock provider 또는 설계 문서 중심으로 설명합니다.

## Links

- GitHub: https://github.com/aile1492
- Notion Portfolio: https://www.notion.so/33413eca6587815c98e5da909b315272
