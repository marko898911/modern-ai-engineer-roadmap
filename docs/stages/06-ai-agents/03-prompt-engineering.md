# 6.3 Prompt Engineering for Agents

## Goal

Prompting an agent is different from prompting a single answer. You are shaping
how the system chooses actions, follows constraints, formats tool calls, and
recovers from errors.

## Roadmap.sh Topics Covered

| Group | Topics |
|---|---|
| Prompt basics | what is prompt engineering |
| Writing good prompts | be specific, provide context, use technical terms, use examples, iterate and test, specify length and format |
| Related path | prompt engineering roadmap |

## Roadmap Item Notes

| Item | Beginner explanation | Agent engineering check |
|---|---|---|
| What is Prompt Engineering? | Prompt engineering is designing the model input so the model understands the task, constraints, context, and output format. | Can you explain every instruction in your system prompt? |
| Be specific in what you want | Vague goals create vague actions. Give the task, success condition, and boundaries. | Does the prompt say when to use tools and when to stop? |
| Provide additional context | Give relevant user state, retrieved docs, tool results, or product rules. | Is the context relevant, current, and clearly separated from instructions? |
| Use relevant technical terms | Precise terms reduce ambiguity. For example, "return JSON matching this schema" is better than "format it nicely." | Are terms defined for the model and the developer? |
| Use examples in your prompt | Examples teach the model the pattern, especially edge cases. | Do examples include failures, refusals, and tool-use decisions? |
| Iterate and test your prompts | Prompt quality is empirical. Change one thing, run the eval, compare results. | Do you track prompt versions and eval scores? |
| Specify length, format, etc. | Output constraints help downstream parsers and users. | Can your parser reject malformed output safely? |
| Prompt Engineering Roadmap | Use it for deeper prompting patterns once your agent loop exists. | Do not use prompt cleverness to replace missing tools or evals. |

## Agent Prompt Anatomy

| Prompt part | Example question |
|---|---|
| Role | What narrow job is this agent doing? |
| Goal | What counts as success for this run? |
| Context | What facts, files, or previous steps matter? |
| Tool policy | Which tools exist, and when should each be used? |
| Safety policy | What actions require refusal, confirmation, or escalation? |
| Output contract | What exact schema or format must be returned? |
| Recovery behavior | What should happen after a tool error or missing data? |

## Learn

| Prompt part | What it should do |
|---|---|
| Role | define the agent's job narrowly |
| Goal | state what success means |
| Context | provide user state, retrieved data, or workflow state |
| Constraints | permissions, safety rules, output boundaries |
| Tool policy | when tools are allowed, required, or forbidden |
| Output format | schema, JSON, markdown, command, or final answer |
| Examples | demonstrate correct decisions and edge cases |

## Build

Create a prompt test suite:

- one system prompt
- one developer/task prompt
- 20 normal cases
- 10 edge cases
- 10 adversarial or confusing cases
- expected behavior for each case

## Measure

Measure:

- instruction-following rate
- schema-valid output rate
- unnecessary tool-call rate
- refusal or escalation correctness
- stability across repeated runs

## Exit Criteria

Move on when you can:

- version prompts like code
- use examples without overfitting the prompt
- distinguish prompt failure from missing tool capability
- write prompts that produce stable structured outputs
- explain why a prompt change improved or harmed eval results

## Study References

- [roadmap.sh Prompt Engineering Roadmap](https://roadmap.sh/prompt-engineering)
- [AI Engineering resources](https://github.com/chiphuyen/aie-book), Chapter 5 topics for prompting and defensive prompting
- [OpenAI structured outputs](https://platform.openai.com/docs/guides/structured-outputs)

## Next

Continue to [6.4 Tools and Actions](04-tools-actions.md).
