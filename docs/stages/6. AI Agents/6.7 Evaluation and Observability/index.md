# 6.7 Evaluation and Observability

## Goal

Agents need stronger evaluation than normal chatbots because they take actions.
You must evaluate final answers, intermediate decisions, tool calls, cost,
latency, and safety behavior.

## Roadmap.sh Topics Covered

| Group | Topics |
|---|---|
| Evaluation and testing | metrics to track, unit testing for tools, integration testing for flows, human-in-the-loop evaluation |
| Evaluation frameworks | LangSmith, Ragas, DeepEval |
| Debugging and monitoring | structured logging and tracing |
| Observability tools | LangSmith, Helicone, LangFuse, openllmetry |

## Roadmap Item Notes

| Item | Beginner explanation | Agent engineering check |
|---|---|---|
| Metrics to Track | Agents need metrics for task success, tool decisions, safety, latency, and cost. | Define release-blocking metrics before optimizing prompts. |
| Unit Testing for Individual Tools | Test each tool without the model. | A broken tool should not be blamed on the LLM. |
| Integration Testing for Flows | Test the full model-tool-memory loop. | Use fixed datasets and compare changes over time. |
| Human in the Loop Evaluation | Humans review ambiguous, high-risk, or subjective outputs. | Create review guidelines so labels are consistent. |
| LangSmith | Tracing/evaluation platform for LangChain and LangGraph workflows. | Use traces to inspect steps, prompts, tool calls, and outputs. |
| Ragas | Evaluation toolkit often used for RAG quality. | Useful when retrieval quality is part of agent success. |
| DeepEval | Evaluation framework for LLM application tests. | Useful for CI-style checks around outputs and behaviors. |
| Structured Logging and Tracing | Logs capture events; traces connect model/tool steps in one run. | Every run should have a run ID and step IDs. |
| Helicone | LLM observability gateway/platform. | Useful for token, cost, latency, and request monitoring. |
| LangFuse | Open-source LLM observability and tracing platform. | Useful for prompt/version traces and production monitoring. |
| openllmetry | OpenTelemetry-style instrumentation for LLM apps. | Useful when you want vendor-neutral traces. |

## Evaluation Layers

| Layer | Example metric |
|---|---|
| Final answer | correctness, citation quality, format validity |
| Tool choice | correct tool selected, unnecessary tool avoided |
| Tool arguments | schema-valid, safe, minimal, authorized |
| Trajectory | completes within max steps, recovers from errors |
| Retrieval | hit rate, groundedness, missing-doc detection |
| Safety | injection blocked, PII not leaked, unsafe write prevented |
| Operations | p95 latency, cost per success, error rate |

`aie-book/chapter-summaries.md` emphasizes that open-ended AI evaluation is
hard and that AI judges should be supplemented with exact and human evaluation.
For agents, this is even more important because the intermediate actions matter
as much as the final text.

## Learn

| Evaluation layer | What to test |
|---|---|
| Tool unit tests | tool behavior without the model |
| Step tests | model chooses correct next action |
| Trajectory tests | full sequence reaches goal safely |
| Final-output tests | answer correctness and formatting |
| Safety tests | injection, privacy, disallowed actions |
| Human review | ambiguous cases and high-impact outputs |
| Observability | traces, spans, tool logs, model calls, cost, latency |

## Build

Create an agent eval harness:

- 30 normal tasks
- 10 edge cases
- 10 adversarial tasks
- tool unit tests
- integration tests for complete flows
- structured trace for each run
- simple report showing pass/fail and failure type

## Measure

Measure:

- task success rate
- tool-call precision
- unnecessary tool-call rate
- invalid tool-call rate
- average steps
- p95 latency
- cost per successful task
- safety failure rate

## Exit Criteria

Move on when you can:

- replay a failed agent trace
- separate model failure from tool failure
- run evals before changing prompts or tools
- track cost and latency per task
- explain which metric blocks release

## Study References

- [AI Engineering resources](https://github.com/chiphuyen/aie-book), Chapters 3, 4, 6, and 10 topics
- `LLM-Engineers-Handbook/llm_engineering/model/evaluation/evaluate.py` for model-as-judge style evaluation code
- [LangSmith](https://docs.smith.langchain.com/)
- [Ragas](https://docs.ragas.io/)
- [DeepEval](https://docs.confident-ai.com/)
- [Langfuse](https://langfuse.com/docs)

## Next

Continue to [6.8 Security and Ethics](<../6.8 Security and Ethics/index.md>).
