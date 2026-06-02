# Temperature, Top-p, Top-k

## Purpose

Explain the main sampling controls that change how predictable or creative an
LLM response becomes.

## Contributor Scope

| Control | Beginner meaning |
|---|---|
| Temperature | changes how strongly the model prefers the most likely token |
| Top-p | keeps the smallest probability mass of likely tokens |
| Top-k | keeps only the top `k` candidate tokens |

## Build

Run the same prompt multiple times with low, medium, and high sampling settings.
Record how correctness, creativity, and format stability change.

## Exit Criteria

You can choose conservative settings for tool calls and more creative settings
for brainstorming.
