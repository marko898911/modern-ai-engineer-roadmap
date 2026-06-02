# Context Windows and Token Based Pricing

## Purpose

Teach context as a limited workspace and token pricing as a real engineering
budget.

## Contributor Scope

| Topic | What to explain |
|---|---|
| Context window | maximum tokens the model can use in one request |
| Input tokens | prompt, messages, tools, retrieved text, memory |
| Output tokens | generated answer or tool arguments |
| Truncation | important text can be cut or buried |
| Cost per task | agent loops multiply token cost across steps |

## Build

Estimate the cost of one agent task with three model calls and two tool
observations.

## Exit Criteria

You can decide what belongs in context, retrieval, memory, or a summary.
