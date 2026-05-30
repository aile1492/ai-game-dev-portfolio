# Code Search Agent

## Summary

Code Search Agent는 코드베이스를 AST 단위와 벡터 검색 기반으로 탐색하고, LLM을 활용해 코드 근거 중심으로 답변하는 AI 개발 생산성 도구입니다.

## Problem

프로젝트 규모가 커질수록 개발자가 겪는 병목은 단순 검색보다 "이 코드가 어디서 호출되고, 어떤 책임을 갖고 있으며, 변경 시 어떤 파일을 함께 봐야 하는가"를 빠르게 파악하는 일입니다.

일반 텍스트 검색만으로는 다음 문제가 남습니다.

- 함수, 클래스, import 경계가 흐려진다.
- 파일 단위 검색 결과가 너무 많다.
- LLM에게 전체 코드를 넣기 어렵다.
- 답변의 근거가 불명확하면 실무에서 신뢰하기 어렵다.

## Approach

```text
Repository
  -> file discovery
  -> AST aware chunking
  -> embedding
  -> vector search
  -> LLM reranking
  -> source based answer
```

## Key Features

- Tree-sitter 기반 코드 chunking
- ChromaDB 기반 vector search
- sentence-transformers 기반 embedding
- LangGraph 기반 단계형 workflow
- multi-provider LLM support
- FastAPI backend
- Next.js, TypeScript frontend
- SSE 기반 진행 상황 스트리밍

## Portfolio Value

이 프로젝트는 AI를 일반 챗봇이 아니라 개발자의 실제 탐색 흐름에 붙이는 경험을 보여줍니다.

- 코드 근거 기반 응답
- 검색, 재정렬, 요약의 단계 분리
- 내부 개발 생산성 도구 방향성
- Agent / Tool-use / Retrieval 구조 이해

## GitHub

https://github.com/aile1492/code-search-agent

## Resume Summary

Code Search Agent는 코드베이스를 AST 단위로 분리하고 vector search와 LLM reranking을 결합해 자연어 질문에 코드 근거 기반으로 답변하는 개발 생산성 도구입니다. 대규모 코드 탐색 병목을 줄이기 위해 검색, 분석, 응답 생성을 단계별 workflow로 구성했습니다.
