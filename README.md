# FinDocs Assistant

![status](https://img.shields.io/badge/status-building-orange)

Financial-document Q&A with streamed answers and sentence-level citations.

**Stack:** React, TypeScript, FastAPI, pgvector

> **Status: Building.** Launching soon.

## Design targets

- **Fast:** under 1 s to first token, on $0/month infrastructure
- **Grounded:** retrieve, answer, then verify pipeline with sentence-level citations
- **Accurate:** 44% to 80% answer accuracy on a 70-question eval set, with 70% fewer unsupported claims
- **Hybrid search:** hit@3 from 62% to 90%
- **Robust:** resists prompt injection in 19 of 20 adversarial documents
- **Tested:** 300+ pytest and Vitest tests using model doubles, under 5 s, no API keys
- **Gated CI:** pull requests checked on tests, lint, types, and Docker builds
- **Swappable models:** Gemini, Groq, or local Qwen

## Features

- Upload and ingestion APIs with SHA-256 deduplication
- Streamed answers with sentence-level citations
- Hybrid (dense + keyword) retrieval on pgvector
- Verify step that checks each claim against its source

## Layout

```
backend/    FastAPI app, ingestion, retrieval, verify step, LLM backends
frontend/   React + TypeScript streaming chat UI with citations
eval/       question set, adversarial docs, metric scripts
docs/       design notes
.github/    CI workflows
```
