# 6.5 Agent Memory

## Goal

Memory lets an agent carry useful state across turns or sessions. Bad memory
pollutes context, stores private data unnecessarily, and makes failures harder
to debug.

## Roadmap.sh Topics Covered

| Group | Topics |
|---|---|
| Memory basics | what is agent memory |
| Types | short-term memory, long-term memory, episodic vs semantic memory |
| Storage | within prompt, vector DB, SQL, custom stores |
| Maintenance | RAG and vector databases, user profile storage, summarization/compression, forgetting/aging strategies |

## Roadmap Item Notes

| Item | Beginner explanation | Agent engineering check |
|---|---|---|
| What is Agent Memory? | Memory is state the agent can use beyond the latest user message. It can be temporary, durable, structured, or retrieved. | Can you say exactly where each memory item is stored and why? |
| Short-Term Memory | Current conversation, current task state, recent tool results, and scratch state. | Does it fit in context without burying the most important instructions? |
| Long-Term Memory | Durable facts across sessions, such as user preferences, project facts, or past decisions. | Does the user know and consent to what is stored? |
| Within Prompt | Memory is inserted directly into the prompt. | Simple and transparent, but expensive and easy to overfill. |
| Vector DB / SQL / Custom | Durable stores for retrieved semantic memories, structured profiles, or domain-specific state. | Choose vector search for fuzzy meaning, SQL for structured facts, custom when access rules matter. |
| Episodic vs Semantic Memory | Episodic memory stores events; semantic memory stores general facts or concepts. | Do not retrieve old events when stable facts are needed, and vice versa. |
| RAG and Vector Databases | RAG retrieves relevant external memory into the prompt. | Evaluate retrieval quality separately from generation quality. |
| User Profile Storage | Stores stable user preferences or account facts. | Keep it minimal, editable, and privacy-aware. |
| Summarization / Compression | Reduces long histories into shorter state. | Summaries can delete important details or preserve wrong ones. Test them. |
| Forgetting / Aging Strategies | Removes stale, low-value, or sensitive memory over time. | Define expiration rules before memory becomes a junk drawer. |

## Memory Decision Rule

Use the smallest memory that solves the problem:

| Need | Use |
|---|---|
| only current task state | short-term state in the loop |
| stable user setting | SQL/profile field |
| many documents | RAG/vector or hybrid retrieval |
| long conversation | rolling summary plus important facts |
| sensitive data | avoid storing, or store with explicit consent and deletion |

## Learn

| Memory type | Use it for | Be careful with |
|---|---|---|
| Short-term | current task state and recent turns | context bloat |
| Long-term | durable facts, preferences, history | privacy and stale facts |
| Episodic | past events and interactions | irrelevant retrieval |
| Semantic | stable knowledge and concepts | over-trusting embeddings |
| Profile | user preferences and settings | consent and PII |

## Build

Run a memory experiment:

- baseline agent with no long-term memory
- agent with summarization memory
- agent with vector memory
- agent with structured profile memory

Use the same 20 tasks for each version.

## Measure

Measure:

- task success
- retrieved-memory relevance
- context token growth
- latency
- stale or wrong memory use
- privacy-sensitive stored fields

## Exit Criteria

Move on when you can:

- explain semantic vs episodic memory
- choose between prompt memory, SQL, and vector search
- design a forgetting policy
- prevent private data from being stored accidentally
- show whether memory improved results in an eval

## Study References

- [AI Engineering resources](https://github.com/chiphuyen/aie-book), Chapter 6 topics on RAG, agents, and memory
- [Hands-On LLMs](https://github.com/HandsOnLLM/Hands-On-Large-Language-Models), Chapters 8 and 10 for semantic search and embeddings
- `LLM-Engineers-Handbook/llm_engineering/application/rag/` for query expansion, reranking, and self-query RAG components

## Next

Continue to [6.6 Architectures and MCP](06-architectures-mcp.md).
