# AI Research Agent

## Summary

AI Research Agent는 사용자의 질문을 하위 질문으로 분해하고, 검색, 페이지 읽기, 분석, 리포트 작성을 순차적으로 수행하는 LangGraph 기반 자율 연구 Agent입니다.

## Problem

기술 리서치나 채용 공고 분석처럼 여러 출처를 읽고 비교해야 하는 업무는 시간이 많이 걸립니다. 단순 챗봇 응답은 빠르지만, 어떤 자료를 근거로 판단했는지 추적하기 어렵습니다.

## Approach

```text
User question
  -> planner
  -> searcher
  -> reader
  -> analyzer
  -> writer
  -> markdown report
```

각 단계는 상태를 공유하며, 진행 상황은 SSE로 frontend에 전달됩니다.

## Key Features

- LangGraph StateGraph 기반 multi step workflow
- Tavily search
- Jina Reader 기반 page reading
- Claude/Groq provider support
- FastAPI backend
- Next.js, TypeScript frontend
- SSE progress timeline
- Markdown report generation

## Portfolio Value

이 프로젝트는 AI Agent를 단순 자동응답이 아니라, 목표를 분해하고 도구를 사용하며 결과물을 만드는 workflow로 구성한 경험을 보여줍니다.

- Agent state 설계
- tool-use workflow 이해
- source based report generation
- 사용자에게 진행 상황을 보여주는 UX

## GitHub

https://github.com/aile1492/ai-research-agent

## Resume Summary

AI Research Agent는 질문을 하위 작업으로 분해하고, 검색, 페이지 읽기, 분석, 리포트 작성을 수행하는 LangGraph 기반 자율 연구 도구입니다. Agent의 단계별 상태와 진행 이벤트를 관리하며 source based report generation 구조를 구현했습니다.
