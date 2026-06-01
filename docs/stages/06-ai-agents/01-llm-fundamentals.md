# 6.1 LLM Fundamentals for Agents

## Goal

An agent is only as good as your understanding of the model inside the loop.
This sub-stage gives you the LLM concepts that matter most for agent behavior,
cost, latency, and reliability.

## Roadmap.sh Topics Covered

| Group | Topics |
|---|---|
| Model mechanics | transformer models, tokenization, context windows, token pricing |
| Model families | open-weight models, closed-weight models, families and licenses |
| Generation controls | temperature, top-p, frequency penalty, presence penalty, stopping criteria, max length |
| Agent-relevant basics | streamed vs unstreamed responses, reasoning vs standard models, fine-tuning vs prompt engineering |
| Retrieval basics | embeddings, vector search, basics of RAG |
| Cost basics | pricing of common models |

## Roadmap Item Notes

| Item | Beginner explanation | Agent engineering check |
|---|---|---|
| Transformer Models and LLMs | Transformers are the architecture family behind most current LLMs. For agents, you only need enough architecture knowledge to reason about tokens, context, attention, latency, and limits. | Can you explain why adding tool schemas and retrieved docs increases prompt size? |
| Tokenization | Text is split into tokens before the model sees it. Token counts drive cost, context usage, truncation, and latency. | Count tokens for a user request, tool list, retrieved context, and final answer. |
| Context Windows | The context window is the maximum amount of input/output the model can handle at once. It is working space, not durable memory. | Decide what must be in context now and what belongs in retrieval or memory. |
| Token Based Pricing | Most hosted models charge by input and output tokens. Agent loops multiply token cost because each step sends more context. | Estimate the cost of one full agent trajectory, not just one model call. |
| Open Weight Models | Model weights are available to run or fine-tune under a license. They can help with privacy and cost, but you own hosting and optimization. | Check license, hardware needs, context length, tool support, and serving cost. |
| Closed Weight Models | You call the model through an API. They often provide strong quality and tool support, but you depend on provider pricing, uptime, and data terms. | Decide whether the task allows external API calls and what data can be sent. |
| Model Families and Licenses | A model family is a related set of models with sizes, variants, and licenses. Licenses decide what you may ship. | Record model name, provider, version, license, and allowed use. |
| Streamed vs Unstreamed Responses | Streaming sends tokens as they are generated. Unstreamed waits for the whole answer. | Stream final user-facing text, but be careful streaming partial tool decisions. |
| Reasoning vs Standard Models | Reasoning models spend more compute on hard problems. They can improve planning, but may be slower and more expensive. | Use reasoning models only when evals show they improve multi-step success. |
| Fine-tuning vs Prompt Engineering | Prompting changes the input; fine-tuning changes model behavior through training. Most agent work starts with prompts, tools, retrieval, and evals. | Fine-tune only after you can show prompting/RAG/tools are the bottleneck. |
| Embeddings and Vector Search | Embeddings turn content into vectors so similar meanings can be retrieved. Vector search is a common agent memory and RAG mechanism. | Measure retrieval hit rate before trusting the agent's answer. |
| Basics of RAG | RAG retrieves outside information and puts it into context before generation. In agents, retrieval is one of the most common tools. | Separate retrieval failure from generation failure in your evals. |
| Pricing of Common Models | Price changes quickly, but the habit matters: compare models by cost per successful task, not cost per token alone. | Track model, input tokens, output tokens, retries, tool calls, and success rate. |

## Generation Controls

These controls change how the model samples output. For agents, they matter
because unstable output can break tool calls, JSON schemas, and decision loops.

| Control | What it does | Beginner rule |
|---|---|---|
| Temperature | Controls randomness. Lower values are more deterministic; higher values explore more varied completions. | Use low temperature for tool calls, extraction, and evals. Raise it only for creative generation. |
| Top-p | Limits sampling to the smallest group of likely tokens whose combined probability reaches `p`. | Usually tune either temperature or top-p, not both at once. |
| Frequency Penalty | Penalizes tokens that have appeared frequently, reducing repetitive phrasing. | Useful for long creative text; risky for structured outputs where repetition may be valid. |
| Presence Penalty | Penalizes tokens once they have appeared at all, nudging the model toward new topics. | Rarely needed for agents; can make the model drift from the task. |
| Stopping Criteria | Defines sequences or conditions where generation should stop. | Use stops to prevent the model from writing past the required format or into another role. |
| Max Length | Caps generated tokens. It protects cost and latency but can truncate reasoning or JSON. | Set a budget large enough for the expected output, then test truncation cases. |

## Local Source Connection

`aie-book/chapter-summaries.md` frames sampling as the source of both useful
creativity and inconsistency. The agent lesson is simple: probabilistic output
must be surrounded by schemas, evals, retries, and logs. `LLM-Engineers-Handbook`
shows this in code by setting sampling parameters during generation and then
running an evaluation pipeline over the outputs.

## Learn

| Topic | Agent implication |
|---|---|
| Tokens | tool schemas, retrieved context, and logs all consume context |
| Context windows | long context can hide important instructions and raise cost |
| Streaming | improves user experience but complicates tool orchestration |
| Reasoning models | may improve planning but cost more and can be slower |
| Generation controls | affect determinism, creativity, and tool-call stability |
| Open vs closed models | affects privacy, latency, hosting, licensing, and tool support |
| RAG | gives agents external knowledge without pretending memory is magic |

## Build

Create an LLM behavior notebook:

- compare streamed and unstreamed responses
- compare a standard model and a reasoning model if available
- inspect token counts for prompts, tool schemas, and retrieved context
- test temperature/top-p effects on structured output
- estimate cost for 100, 1,000, and 10,000 agent tasks

## Measure

Measure:

- input tokens
- output tokens
- latency
- cost estimate
- JSON or schema-valid output rate
- answer stability over repeated runs

## Exit Criteria

Move on when you can:

- explain why context length is a budget, not free memory
- choose generation settings for tool calling
- estimate cost before running a large eval
- explain when RAG is better than fine-tuning
- explain when a reasoning model is worth the cost

## Study References

- [Hands-On Large Language Models](https://github.com/HandsOnLLM/Hands-On-Large-Language-Models), Chapters 1 to 3 for tokenization and transformers
- [AI Engineering resources](https://github.com/chiphuyen/aie-book), Chapters 2, 6, 7, and 9 topics
- [OpenAI advanced usage](https://platform.openai.com/docs/guides/advanced-usage) for generation parameters
- [OpenAI structured outputs](https://platform.openai.com/docs/guides/structured-outputs) for schema-constrained model output
- `LLM-Engineers-Handbook/llm_engineering/model/evaluation/evaluate.py` for generation plus evaluation flow

## Next

Continue to [6.2 Agents 101](02-agents-101.md).
