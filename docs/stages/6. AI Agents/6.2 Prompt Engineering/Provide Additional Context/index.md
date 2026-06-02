# Provide Additional Context

## Goal

Learn how to add the background information a model needs to answer the right
question, for the right user, in the right format.

Context is not filler. It is the operating environment for the prompt: the
user's situation, the task constraints, the source material, and the rules the
model should respect.

## Learn

Start with the difference between the instruction and the context.

| Prompt part | Role | Example |
|---|---|---|
| Instruction | What the model should do | `Draft a customer reply.` |
| Context | What the model should know | `The customer paid for overnight shipping, but the carrier delayed delivery by two days.` |
| Constraints | What the model must respect | `Do not promise a refund. Offer tracking help and escalation.` |
| Output format | How the answer should look | `Use three short paragraphs and a subject line.` |

Useful context can include:

- user state
- retrieved documents
- tool results
- product rules
- trusted instructions versus untrusted evidence
- the target audience
- prior conversation turns
- examples of the desired output

The reference article frames context as background information that helps the
model understand the request, and it separates directly supplied prompt context
from external context such as available data or retrieval sources. It also
warns that both too little context and too much context can reduce answer
quality.

## Context Checklist

Before adding context, ask:

| Question | Why it matters |
|---|---|
| What ambiguity could the model resolve incorrectly? | Prevents broad or off-target answers. |
| Which facts are required to complete the task? | Keeps the prompt focused. |
| Which facts are only supporting evidence? | Helps separate trusted instructions from data. |
| Are any sources untrusted? | Prevents documents or tool output from overriding system rules. |
| What should the model ignore? | Reduces distraction from irrelevant details. |

Good context is specific, relevant, and easy to scan. If the context is long,
use labels:

```text
Task:
Summarize the support issue and suggest the next action.

User state:
- Plan: Pro
- Region: EU
- Last payment: successful

Trusted policy:
- Do not offer account credits without manager approval.
- Escalate billing disputes over $500.

Customer message:
"I was charged twice and need this fixed today."
```

## Build

Create two prompts for the same task.

### Prompt A: No Context

```text
Write a response to a customer who has a billing problem.
```

### Prompt B: Relevant Context

```text
Task:
Write a support response.

Customer context:
- The customer is on the Pro plan.
- They were charged twice for the same invoice.
- They are asking for help today.

Policy context:
- Apologize for the inconvenience.
- Do not promise a refund until billing verifies the duplicate charge.
- Offer to escalate to billing and ask for the invoice number.

Output:
- 120 words or fewer.
- Calm, direct, and professional.
```

Compare the answers and identify:

- which answer is more specific
- which answer follows policy better
- which answer asks for the right missing information
- whether any context was unnecessary

## Measure

A context-rich prompt is working when the output:

- answers the intended question instead of a generic version of the question
- uses the supplied facts correctly
- does not invent missing facts
- follows trusted rules over untrusted source text
- stays focused despite extra information

## Exit Criteria

You can add context without burying the main instruction, and you can explain
why each piece of context is included.

## Common Mistake

Do not paste everything you know into the prompt. Long context can dilute the
task, distract the model, or push important instructions out of the usable
context window. Prefer the smallest set of facts, rules, examples, and evidence
needed for the current answer.

## Next

Move to examples after you can provide context cleanly. Examples show the model
the pattern of answer you want, while context gives it the facts and constraints
needed for this specific task.

## Resource

- [What is Context in Prompt Engineering? Here's Everything You Need To Know](https://godofprompt.ai/blog/what-is-context-in-prompt-engineering/)
