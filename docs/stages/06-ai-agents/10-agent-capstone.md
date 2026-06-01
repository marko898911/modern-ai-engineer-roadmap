# 6.10 Agent Capstone

## Goal

Integrate the whole AI Agents stage into one bounded, measurable,
production-style system.

## Capstone Options

Choose one:

| Capstone | Tools |
|---|---|
| Research assistant | web/search, RAG, citation checker, note writer |
| Repo triage agent | file search, issue classifier, test runner, PR summary |
| Data analysis agent | SQL/query, Python REPL, chart generator, report writer |
| Personal workflow agent | calendar/task API, email draft, preference memory |
| Learning tutor agent | RAG over notes, quiz generator, progress memory |

## Required Architecture

Your capstone must include:

- user input
- system/developer prompt
- structured output
- at least three tools
- short-term state
- one long-term memory mechanism
- max-step limit
- retry/error handling
- eval suite
- tracing
- security tests
- README with architecture and failure analysis

## Roadmap Item Integration

| Roadmap area | What the capstone must show |
|---|---|
| Prerequisites | tool APIs or CLI commands that are testable without the model |
| LLM fundamentals | documented model choice, generation settings, context budget, and cost estimate |
| Agents 101 | clear loop, stop condition, and reason this should be an agent |
| Prompt engineering | versioned prompts and prompt eval cases |
| Tools/actions | at least three typed tools with errors and permissions |
| Memory | one memory mechanism with an eval proving whether it helps |
| Architectures/MCP | chosen architecture and why simpler alternatives were rejected |
| Building agents | manual or framework implementation with retry and timeout handling |
| Evaluation/observability | task evals, traces, latency, cost, and failure buckets |
| Security/ethics | threat model, injection tests, PII/log policy, and write-action controls |

## Recommended README Outline

```text
# Agent Capstone

## Problem
## Why This Needs an Agent
## Architecture
## Model and Generation Settings
## Tools
## Memory
## Evaluation
## Observability
## Security
## Results
## Failure Cases
## Future Work
```

## Build

Build one complete agent and document:

- why it should be an agent instead of a normal workflow
- model choice
- tool schemas
- memory design
- architecture pattern
- eval design
- monitoring design
- security policy

## Measure

Measure:

- task success rate
- average steps per task
- tool-call accuracy
- invalid tool calls
- latency
- cost
- memory usefulness
- injection failure rate

## Exit Criteria

You complete Stage 6 when you can:

- demo the agent end to end
- run the eval suite
- inspect traces for a failed run
- explain the architecture tradeoffs
- explain the security boundaries
- identify what should be improved next

## Next

Continue to [Stage 7: Model Infrastructure](../07-model-infrastructure.md).
