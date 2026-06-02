# 6.1 LLM Fundamentals

## Goal

Understand the model behavior that directly affects agent reliability, cost,
latency, and output stability. This sub-stage now keeps each concept in a
separate part folder so contributors can improve one topic without touching the
whole roadmap.

## Parts

| Part | What contributors should cover |
|---|---|
| [Agent Loop](<Agent Loop/index.md>) | perception, planning, action, observation, reflection, stop condition |
| [Tokenization](<Tokenization/index.md>) | how text becomes tokens and why token counts matter |
| [Context Windows and Token Based Pricing](<Context Windows and Token Based Pricing/index.md>) | context limits, truncation, cost, and latency |
| [Temperature, Top-p, Top-k](<Temperature, Top-p, Top-k/index.md>) | sampling controls and when to use each one |
| [Frequency and Presence Penalty](<Frequency and Presence Penalty/index.md>) | repetition control and topic-drift risks |
| [Stopping Criteria and Max Length](<Stopping Criteria and Max Length/index.md>) | output budgets, stop sequences, and truncation tests |

## Exit Criteria

Move on when you can:

- draw the basic agent loop
- estimate token usage for one agent step
- explain why context length is a budget, not memory
- choose sampling settings for tool calls versus creative writing
- test whether output limits break structured responses

## Next

Continue to [6.2 Prompt Engineering](<../6.2 Prompt Engineering/index.md>).
