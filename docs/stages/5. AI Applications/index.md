# Stage 5: AI Applications

<span class="stage-badge">5</span> Build useful systems around models: context, RAG, evaluation, product flow, and feedback.

## Goal

Most AI engineering work is not training a foundation model. It is adapting
models to real tasks with context, prompts, retrieval, tools, evals, guardrails,
observability, and feedback loops.

## Learn

| Topic | What to understand |
|---|---|
| Prompt engineering | instructions, examples, constraints, formatting, prompt versioning |
| RAG | chunking, embeddings, indexing, retrieval, reranking, generation |
| Evaluation | golden sets, regression tests, human review, model-as-judge |
| UX | uncertainty, citations, corrections, escalation, feedback capture |
| Data feedback | logs, labels, user feedback, failure buckets |
| Guardrails | input/output validation, policy checks, PII handling |

## Build

Build an evaluated RAG application:

- ingest 20 to 100 documents
- implement chunking, embeddings, vector search, and answer generation
- create at least 50 test questions
- measure retrieval and answer quality
- log cost, latency, and failures

## Measure

Measure:

- retrieval recall or hit rate
- answer correctness
- hallucination rate on unknown questions
- latency
- token cost
- failure categories

## Exit Criteria

Move on when you can:

- explain why naive RAG fails
- design a retrieval evaluation set
- choose chunking and embedding strategies intentionally
- distinguish retrieval failure from generation failure
- add a feedback loop to improve the system

## Practical Rule

Every AI application needs a test set before it needs a bigger model.

## Next

Continue to [Stage 6: AI Agents](<../6. AI Agents/index.md>) or [Stage 7: Model Infrastructure](<../7. Model Infrastructure/index.md>).
