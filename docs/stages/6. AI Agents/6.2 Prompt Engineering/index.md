# 6.2 Prompt Engineering

## Goal

Prompting an agent is different from prompting a single answer. You are shaping
how the system chooses actions, follows constraints, formats tool calls, and
recovers from errors.

## Parts

| Part | What contributors should cover |
|---|---|
| [Overview](<Overview/index.md>) | what prompt engineering means for agents |
| [Be Specific in What You Want](<Be Specific in What You Want/index.md>) | task, audience, success condition, boundaries |
| [Provide Additional Context](<Provide Additional Context/index.md>) | relevant facts, retrieved data, user state, tool results |
| [Use Relevant Technical Terms](<Use Relevant Technical Terms/index.md>) | precise terms, schemas, constraints, definitions |
| [Use Examples in Your Prompt](<Use Examples in Your Prompt/index.md>) | normal, edge, refusal, and tool-use examples |
| [Iterate and Test Your Prompts](<Iterate and Test Your Prompts/index.md>) | prompt versions, eval cases, regression testing |
| [Specify Length, Format, etc](<Specify Length, Format, etc/index.md>) | length, format, schema, style, parser safety |
| [Prompt Engineering Roadmap](<Prompt Engineering Roadmap/index.md>) | deeper structure from roadmap.sh prompt engineering |

## Public Labels

The visible labels use corrected public-documentation names:

- `Be Specific in What You Want`
- `Model Families and Licenses`
- `Specify Length, Format, etc`

## Exit Criteria

Move on when you can:

- write a prompt with role, goal, context, constraints, and output format
- include examples without overfitting the prompt
- test prompts against normal, edge, and adversarial cases
- explain why a prompt change improved or harmed the eval result

## Next

Continue to [6.3 Tools and Actions](<../6.3 Tools and Actions/index.md>).
