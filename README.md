# FinDocs Assistant

![status](https://img.shields.io/badge/status-building-orange)

Financial-document Q&A with streamed answers and sentence-level citations.

**Stack:** React, TypeScript, FastAPI, pgvector

> **Status: Building.** Launching soon.

## Highlights

- Streamed answers with sentence-level citations, under 1 s to first token on $0/month infrastructure
- Upload and ingestion APIs with SHA-256 deduplication
- Retrieve, answer, then verify pipeline: accuracy up from 44% to 80% on 70 questions, 70% fewer unsupported claims
- Hybrid search: hit@3 up from 62% to 90%
- Resisted prompt injection in 19 of 20 adversarial documents
- 300+ pytest and Vitest tests using model doubles, running in under 5 s with no API keys
- Pull requests gated on tests, lint, types, and Docker builds
- Swappable Gemini, Groq, and local Qwen backends

## Layout

```
backend/    FastAPI app, ingestion, retrieval, verify step, LLM backends
frontend/   React + TypeScript streaming chat UI with citations
eval/       question set, adversarial docs, metric scripts
docs/       design notes
.github/    CI workflows
```
