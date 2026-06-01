# Stage 6: AI Agents

<span class="stage-badge">6</span> Build agents as controlled systems, not as vague autonomy.

## Goal

An AI agent is a model-driven loop that can inspect state, reason or plan, call
tools, observe results, update memory, and continue toward a goal. The hard
part is not making a model call a tool. The hard part is making the loop
reliable, debuggable, secure, and useful.

This stage incorporates the uploaded `ai-agents.pdf` roadmap: prerequisites,
LLM fundamentals, prompt engineering, tools, MCP, memory, agent architectures,
frameworks, evaluation, monitoring, and security.

## Learn

| Area | What to understand |
|---|---|
| Agent loop | perception, reasoning/planning, action, observation, reflection |
| Prompting | goal, context, constraints, examples, output format |
| Tools | names, descriptions, schemas, error handling, permissions |
| Function calling | structured tool invocation from model outputs |
| MCP | hosts, clients, servers, tools, resources, prompts |
| Memory | short-term context, long-term stores, semantic vs episodic memory |
| Architectures | ReAct, planner-executor, DAG agents, multi-agent patterns |
| Frameworks | LangGraph, LlamaIndex, AutoGen, CrewAI, OpenAI Agents SDK |
| Evaluation | tool unit tests, trajectory tests, task success, human review |
| Observability | traces, spans, tool logs, replay, cost and latency |
| Security | prompt injection, tool misuse, sandboxing, PII, least privilege |

## Build

Build two agents:

1. A manual agent loop from scratch using direct model calls and tool schemas.
2. A framework-based agent with tracing, memory, and at least three tools.

The agent should solve a bounded workflow such as research assistance, repo
triage, data analysis, calendar planning, or codebase Q&A.

## Measure

Measure:

- task success rate on 20 to 50 tasks
- tool-call accuracy
- invalid tool calls
- average steps per task
- latency and cost
- prompt-injection failures
- recovery from tool errors

## Exit Criteria

Move on when you can:

- write an agent loop without a framework
- define safe tool schemas and permissions
- explain when memory helps and when it pollutes context
- trace a failed agent run and identify the failing step
- defend the agent against basic prompt injection and unsafe tool use

## Build Order

1. Direct API call with structured output.
2. Single tool call.
3. Multi-tool loop with max-step limit.
4. Tool error recovery.
5. RAG-backed memory.
6. Framework implementation.
7. Tracing and eval harness.
8. Security tests.

## Common Mistake

Do not begin with many agents. Start with one reliable loop. Multi-agent
systems multiply unclear goals, hidden state, cost, latency, and failure modes.

## Next

Continue to [Stage 7: Model Infrastructure](07-model-infrastructure.md).
