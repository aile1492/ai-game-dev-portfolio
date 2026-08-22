# Code Search Agent

## 한 줄 소개

개발자가 자연어로 질문하면 큰 코드 프로젝트에서 관련 파일과 함수를 찾아 코드 근거와 함께 답변하는 검색 도구입니다.

## 해결하려던 문제

단순한 단어 검색만으로는 이름은 다르지만 역할이 비슷한 코드를 찾기 어렵습니다. 큰 프로젝트에서는 기능이 어디에서 처리되는지 파악하는 데 많은 시간이 듭니다.

## 구현 방식

- 코드를 함수, 클래스, 메서드처럼 의미 있는 단위로 나눕니다.
- 질문의 의미와 가까운 코드 조각을 찾습니다.
- AI가 검색 결과를 다시 비교해 관련성이 높은 코드를 선택합니다.
- 선택된 코드만 근거로 답변합니다.
- 후속 질문에서도 앞선 대화의 맥락을 유지합니다.

## 주요 기능

- Python, JavaScript, TypeScript, Java, C++, Go, Rust 코드 분석
- Tree-sitter를 활용한 코드 구조 분석
- ChromaDB를 활용한 의미 기반 검색
- 여러 AI 모델 제공자 선택
- 생성 중인 답변을 화면에 순서대로 전달

## 사용 기술

Python, FastAPI, LangGraph, Tree-sitter, ChromaDB, Next.js, TypeScript

## 확인 자료

[GitHub 저장소](https://github.com/aile1492/code-search-agent)
