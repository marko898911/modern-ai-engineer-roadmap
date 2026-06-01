# Stage 6: AI Agents

<span class="stage-badge">6</span> Build agents as controlled systems, not as vague autonomy.

## Goal

An AI agent is a model-driven loop that can inspect state, reason or plan, call
tools, observe results, update memory, and continue toward a goal. The hard
part is not making a model call a tool. The hard part is making the loop
reliable, debuggable, secure, and useful.

This stage follows the structure of the live [roadmap.sh AI Agents
Roadmap](https://roadmap.sh/ai-agents), plus the uploaded `ai-agents.pdf`, but
converts the visual roadmap into a student-friendly build path.

## Sub-Stage Ladder

| Sub-stage | Focus | Main output |
|---|---|---|
| [6.0 Prerequisites](06-ai-agents/00-prerequisites.md) | backend basics, Git, terminal, APIs | API-backed tool server |
| [6.1 LLM Fundamentals](06-ai-agents/01-llm-fundamentals.md) | models, tokens, context, pricing, generation controls | LLM behavior notebook |
| [6.2 Agents 101](06-ai-agents/02-agents-101.md) | agent loop and use cases | paper agent design |
| [6.3 Prompt Engineering](06-ai-agents/03-prompt-engineering.md) | instructions, examples, formats, iteration | prompt test suite |
| [6.4 Tools and Actions](06-ai-agents/04-tools-actions.md) | tool schemas, errors, permissions | three production-style tools |
| [6.5 Agent Memory](06-ai-agents/05-agent-memory.md) | short-term, long-term, episodic, semantic memory | memory experiment |
| [6.6 Architectures and MCP](06-ai-agents/06-architectures-mcp.md) | ReAct, planner-executor, DAG, MCP | architecture comparison |
| [6.7 Building Agents](06-ai-agents/07-building-agents.md) | manual loop, function calling, frameworks | two working agents |
| [6.8 Evaluation and Observability](06-ai-agents/08-evaluation-observability.md) | tests, metrics, tracing, monitoring | eval and trace dashboard |
| [6.9 Security and Ethics](06-ai-agents/09-security-ethics.md) | injection, sandboxing, PII, bias, red teaming | agent threat model |
| [6.10 Capstone](06-ai-agents/10-agent-capstone.md) | integrate everything | bounded production-style agent |

## What You Build Across This Stage

You will build one agent system in layers:

```text
LLM call
  -> structured output
  -> one safe tool
  -> multi-tool loop
  -> memory
  -> framework implementation
  -> eval suite
  -> traces and monitoring
  -> security tests
  -> capstone agent
```

## Completion Standard

By the end of Stage 6, you should have:

- a manual agent loop from scratch
- a framework-based agent
- at least three typed tools
- short-term and long-term memory experiments
- task evals with success/failure categories
- structured traces
- prompt-injection and tool-abuse tests
- a clear README explaining architecture, tradeoffs, and limits

## Common Mistake

Do not begin with many agents. Start with one reliable loop. Multi-agent
systems multiply unclear goals, hidden state, cost, latency, and failure modes.

## Next

Start with [6.0 Prerequisites](06-ai-agents/00-prerequisites.md), then continue
through the sub-stages in order.
