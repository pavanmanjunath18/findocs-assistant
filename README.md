# FinDocs Assistant

![status](https://img.shields.io/badge/status-building-orange)

Financial-document Q&A with streamed answers and sentence-level citations.

**Stack:** React, TypeScript, FastAPI, pgvector

> **Status: 🚧 Building.** The numbers below are the **targets** this project is being built to hit.
> None are measured results yet. Each row flips to ✅ only when backed by a reproducible run in `eval/`.

## Targets

| Area | Target | Status |
|---|---|---|
| Latency | < 1 s to first token | ⬜ not started |
| Cost | $0/month infrastructure | ⬜ not started |
| Ingestion | Upload + ingestion APIs, SHA-256 deduplication | ⬜ not started |
| Pipeline | Retrieve → answer → verify, with streamed sentence-level citations | ⬜ not started |
| Answer accuracy | 44% → 80% on a 70-question eval set | ⬜ baseline not measured |
| Unsupported claims | 70% reduction (verify step on vs. off) | ⬜ not started |
| Retrieval | Hybrid search: hit@3 62% → 90% | ⬜ baseline not measured |
| Security | Resist prompt injection in 19 of 20 adversarial documents | ⬜ not started |
| Tests | 300+ pytest + Vitest tests, < 5 s, no API keys (model doubles) | ⬜ 0 / 300 |
| CI | PRs gated on tests, lint, types, Docker build | ⬜ not started |
| Backends | Swappable Gemini, Groq, local Qwen | ⬜ not started |

## Planned layout

```
backend/    FastAPI app, ingestion, retrieval, verify step, LLM backends
frontend/   React + TypeScript streaming chat UI with citations
eval/       70-question set, 20 adversarial docs, reproducible metric scripts
docs/       design notes, results
.github/    CI workflows
```

## Roadmap

- [ ] Backend skeleton, upload + SHA-256 dedup, pgvector schema
- [ ] Chunking, embeddings, dense + keyword hybrid retrieval
- [ ] Streamed answer endpoint with sentence-level citations
- [ ] Verify step (claim-vs-source check)
- [ ] LLM backend interface: Gemini, Groq, local Qwen
- [ ] React UI with streaming and citation highlighting
- [ ] Eval harness: 70 questions, hit@3, accuracy, unsupported-claim rate, injection set
- [ ] Test suite with model doubles (300+, < 5 s)
- [ ] CI: tests, lint, types, Docker build
- [ ] Deploy on free tier; measure time to first token

## Results

_Pending. Will be filled in from `eval/` runs, with the commands to reproduce them._
