# Stage 4: Large Language Models

<span class="stage-badge">4</span> Learn what LLMs are, how they generate text, and where their limits come from.

## Goal

LLM engineering is not only prompting. You need a mental model of tokenization,
embeddings, transformer blocks, attention, context windows, sampling, structured
outputs, fine-tuning, and inference cost.

## Learn

| Topic | What to understand |
|---|---|
| Tokenization | tokens, subwords, token counts, multilingual issues |
| Embeddings | vector meaning, similarity, retrieval use |
| Transformer blocks | attention, MLP, residuals, normalization, positional encoding |
| Generation | logits, temperature, top-p, stopping, structured output |
| Model types | closed API, open-weight, base, instruct, reasoning, multimodal |
| Fine-tuning | SFT, preference tuning, LoRA, when not to fine-tune |
| Evaluation | task evals, regression tests, model-as-judge limits |
| Cost and latency | context length, output length, batching, model size |

## Build

Create an LLM fundamentals notebook:

- tokenize sample inputs and inspect token counts
- compare at least two models on the same tasks
- use structured output for one task
- build a small embedding search demo
- record cost, latency, and failure cases

## Measure

Measure:

- prompt tokens and output tokens
- latency
- cost estimate
- structured output validity
- accuracy on a small hand-built test set

## Exit Criteria

Move on when you can:

- explain why context length is not the same as memory
- explain why models hallucinate
- choose between prompting, RAG, and fine-tuning for a task
- describe how temperature and top-p change generation
- build a small embedding search example

## Common Mistake

Do not start by fine-tuning. First prove that prompting, retrieval, tools,
better data, or a different model cannot solve the problem more simply.

## Next

Continue to [Stage 5: AI Applications](05-ai-applications.md).
