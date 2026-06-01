# 6.2 Agents 101

## Goal

Understand what an agent is, what a tool is, and why the agent loop is the core
unit of agent engineering.

## Roadmap.sh Topics Covered

| Group | Topics |
|---|---|
| Agent basics | what are AI agents, what are tools |
| Agent loop | perception/user input, reason and plan, action/tool invocation, observation and reflection |
| Example use cases | personal assistant, code generation, data analysis, web scraping/crawling, NPC/game AI |

## Roadmap Item Notes

| Item | Beginner explanation | Agent engineering check |
|---|---|---|
| What are AI Agents? | An AI agent uses a model to choose steps toward a goal, often by using tools and state across multiple turns. | Can you name the goal, environment, tools, and stop condition? |
| What are Tools? | Tools are external capabilities the model can request, such as search, code execution, database lookup, or sending a message. | Can each tool be tested without the model? |
| Perception / User Input | The agent receives a task, conversation, file, event, or environment state. | Is the input trusted, untrusted, or mixed? |
| Reason and Plan | The model decides what information is missing and what action should happen next. | Is planning actually needed, or would a fixed workflow be safer? |
| Acting / Tool Invocation | The agent calls a tool with structured arguments. | Are tool arguments validated before execution? |
| Observation and Reflection | The agent reads tool results, updates state, and decides whether to continue. | Can the agent detect failed, empty, or suspicious tool results? |
| Personal Assistant | Helps with schedules, tasks, email drafts, reminders, or personal knowledge. | Requires strong privacy, permissions, and confirmation for write actions. |
| Code Generation | Reads, edits, tests, and explains code. | Requires sandboxing, clean diffs, and test execution boundaries. |
| Data Analysis | Queries data, writes code, creates charts, and explains results. | Requires dataset permissions and protection against misleading analysis. |
| Web Scraping / Crawling | Searches or extracts information from webpages. | Treat webpages as untrusted because they can contain prompt injection. |
| NPC / Game AI | Controls game characters or simulations. | Needs fast, bounded decisions and deterministic fallback behavior. |

## Agent or Workflow?

Use an agent when the next step depends on uncertain state or model judgment.
Use a workflow when the steps are known in advance. A good modern AI product
often combines both: deterministic workflow around a few model decisions.

## Learn

| Concept | Practical meaning |
|---|---|
| Perception | collect user input, state, documents, events, or environment signals |
| Reason and plan | decide next step; sometimes one step is enough |
| Action | call a tool, API, function, browser, shell, database, or workflow |
| Observation | inspect tool output and decide whether to continue |
| Reflection | summarize progress, catch errors, or revise plan |
| Stop condition | decide when the loop is done or should fail safely |

## Build

Design an agent on paper before coding:

- goal
- target user
- tools needed
- inputs and outputs
- loop steps
- stop conditions
- failure modes
- safety boundaries

Then implement a fake-agent simulation where the "model" is just deterministic
Python logic. This removes model randomness and helps you see the loop.

## Measure

Measure:

- number of steps per task
- possible failure points
- missing tool permissions
- ambiguous instructions
- cases where a workflow is better than an agent

## Exit Criteria

Move on when you can:

- explain agent vs chatbot vs workflow
- draw the loop for a chosen use case
- identify which steps need model judgment
- identify which steps should be deterministic code
- define a stop condition and max-step limit

## Study References

- [AI Engineering resources](https://github.com/chiphuyen/aie-book), Chapter 6 topics for RAG and agents
- [Hands-On LLMs agent bonus](https://github.com/HandsOnLLM/Hands-On-Large-Language-Models/blob/main/bonus/9_agents.md)
- `building-llm-applications/ch11/main_02_02.py` for a simple tool-using agent loop

## Next

Continue to [6.3 Prompt Engineering](03-prompt-engineering.md).
