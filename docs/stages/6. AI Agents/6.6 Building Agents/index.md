# 6.6 Building Agents

## Goal

Build agents two ways: manually, so you understand the loop, and with
frameworks, so you understand what the framework gives you and hides from you.

## Roadmap.sh Topics Covered

| Group | Topics |
|---|---|
| Manual from scratch | direct LLM API calls, implementing the agent loop, parsing model output, error and rate-limit handling |
| LLM-native function calling | OpenAI function calling, Gemini function calling, Anthropic tool use, OpenAI Assistant API |
| Frameworks | LangChain, LangGraph, LlamaIndex, Haystack, AutoGen, CrewAI, Agno, Smol Depot |

## Roadmap Item Notes

| Item | Beginner explanation | Agent engineering check |
|---|---|---|
| Manual from Scratch | You write the loop yourself: call model, parse output, execute tool, append observation, repeat. | Can you explain every message sent to the model? |
| Direct LLM API Calls | You call a provider or local server directly. | Log model, parameters, tokens, latency, and raw outputs. |
| Implementing the Agent Loop | The loop controls state, tool execution, observations, and stop conditions. | Include max steps, timeout, and safe failure behavior. |
| Parsing Model Output | Convert model text or tool calls into structured actions. | Reject malformed output instead of guessing silently. |
| Error and Rate-Limit Handling | APIs and tools fail. Agents must retry, back off, or ask for help. | Separate retryable errors from permanent errors. |
| LLM Native Function Calling | Provider APIs can return structured tool calls directly. | Still validate arguments before executing tools. |
| OpenAI Function Calling | OpenAI's tool calling lets models select functions and provide JSON-like arguments. | Use strict schemas when possible and test invalid arguments. |
| Gemini Function Calling | Gemini provides provider-native function/tool calling. | Keep provider-specific behavior behind an adapter. |
| Anthropic Tool Use | Anthropic models can request tool use through structured content blocks. | Normalize tool results before returning them to the loop. |
| OpenAI Assistant API | A higher-level API for assistant-style workflows. | Understand what state and orchestration it owns for you. |
| LangChain | General LLM application toolkit. | Useful ecosystem, but keep your own evals and boundaries. |
| LangGraph | Graph/state-machine style agent orchestration. | Good when you need explicit state, branches, and durable flows. |
| LlamaIndex | Strong for data connectors, RAG, and knowledge agents. | Useful when retrieval and document workflows dominate. |
| Haystack | Pipeline-oriented framework for search and NLP systems. | Useful for production retrieval pipelines. |
| AutoGen | Multi-agent conversation and collaboration framework. | Use after one-agent design is insufficient. |
| CrewAI | Role-based multi-agent workflow framework. | Good for demos and role workflows; measure overhead. |
| Agno | Agent framework focused on practical tool-using assistants. | Evaluate fit against your state, tooling, and deployment needs. |
| Smol Depot | Small-agent ecosystem/resource referenced by roadmap.sh. | Treat as optional exploration, not a core dependency. |

## Manual Loop Skeleton

```text
messages = [system, user]
for step in range(max_steps):
    model_output = call_model(messages, tools)
    if model_output.final_answer:
        return model_output.final_answer
    action = validate_tool_call(model_output.tool_call)
    observation = run_tool(action)
    messages.append(observation)
return safe_failure("max steps reached")
```

The code examples in `building-llm-applications/ch11` show this idea with
LangGraph: the model produces tool calls, a tool node executes them, and tool
messages are appended back to state.

## Learn

| Build style | Learn this |
|---|---|
| Direct API | exact model inputs, outputs, retries, and token costs |
| Structured outputs | schema validation and repair |
| Function calling | provider-native tool invocation |
| Frameworks | state graphs, tools, memory, tracing, retries, orchestration |
| Error handling | rate limits, tool failures, malformed outputs, timeouts |

## Build

Build two versions of the same bounded agent:

1. Manual agent loop from scratch.
2. Framework-based agent using LangGraph, LlamaIndex, AutoGen, CrewAI, Haystack, Agno, or another current framework.

The agent should have:

- max-step limit
- three tools
- structured output
- retries
- timeout handling
- tool error recovery
- final answer with evidence or trace summary

## Measure

Measure:

- task success
- model calls per task
- invalid tool calls
- retry count
- p50 and p95 latency
- token cost
- ease of debugging

## Exit Criteria

Move on when you can:

- write a manual loop without copying a framework
- explain provider-native function calling
- explain what your chosen framework abstracts away
- handle malformed model output
- recover from rate limits and tool errors

## Study References

- [OpenAI function calling](https://platform.openai.com/docs/guides/function-calling)
- [OpenAI Agents guide](https://platform.openai.com/docs/guides/agents)
- [LangGraph docs](https://langchain-ai.github.io/langgraph/)
- `building-llm-applications/ch11/` for progressively richer LangGraph agent examples

## Next

Continue to [6.7 Evaluation and Observability](<../6.7 Evaluation and Observability/index.md>).
