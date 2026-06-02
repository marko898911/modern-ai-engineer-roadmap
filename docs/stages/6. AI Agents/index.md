# Stage 6: AI Agents

<span class="stage-badge">6</span> Build agents as controlled systems, not as vague autonomy.

## Goal

An AI agent is a model-driven loop that can inspect state, plan, call tools,
observe results, update memory, and continue toward a goal. The hard part is
not making a model call a tool. The hard part is making the loop reliable,
debuggable, secure, and useful.

## Contributor Structure

Stage 6 now uses a folder-first structure:

```text
6. AI Agents/
|-- 6.0 Prerequisites/
|   |-- Basic Knowledge/
|   `-- ...
|-- 6.1 LLM Fundamentals/
|   |-- Agent Loop/
|   `-- ...
`-- 6.2 Prompt Engineering/
    |-- Overview/
    |-- Prompt Engineering Roadmap/
    `-- ...
```

Managers control the sub-stage and part names in `mkdocs.yml`. Contributors
work inside the matching part folder and edit that folder's `index.md`.

## Sub-Stage Ladder

| Sub-stage | Manager focus | Contributor unit |
|---|---|---|
| [6.0 Prerequisites](<6.0 Prerequisites/index.md>) | foundation vocabulary before agent work | one part folder |
| [6.1 LLM Fundamentals](<6.1 LLM Fundamentals/index.md>) | LLM behavior that affects agents | one part folder |
| [6.2 Prompt Engineering](<6.2 Prompt Engineering/index.md>) | prompts for reliable agent behavior | one part folder |
| [6.3 Tools and Actions](<6.3 Tools and Actions/index.md>) | tool schemas, errors, permissions | future part folders |
| [6.4 Agent Memory](<6.4 Agent Memory/index.md>) | short-term and long-term state | future part folders |
| [6.5 Architectures and MCP](<6.5 Architectures and MCP/index.md>) | ReAct, planner-executor, DAG, MCP | future part folders |
| [6.6 Building Agents](<6.6 Building Agents/index.md>) | manual loop, function calling, frameworks | future part folders |
| [6.7 Evaluation and Observability](<6.7 Evaluation and Observability/index.md>) | tests, metrics, tracing, monitoring | future part folders |
| [6.8 Security and Ethics](<6.8 Security and Ethics/index.md>) | injection, sandboxing, privacy, bias | future part folders |
| [6.9 Capstone](<6.9 Capstone/index.md>) | integrate everything | future part folders |

## Naming Rules

- Folder names match the visible sub-stage or part name.
- Each folder owns one `index.md`.
- Avoid hidden child-topic files; put contributor work in the part page.
- When a manager renames a part, rename both the folder and the matching nav
  entry.

## Completion Standard

By the end of Stage 6, you should have:

- a manual agent loop from scratch
- a framework-based agent
- at least three typed tools
- short-term and long-term memory experiments
- task evals with success/failure categories
- structured traces
- prompt-injection and tool-abuse tests
- a clear README explaining architecture, tradeoffs, and limits

## Next

Start with [6.0 Prerequisites](<6.0 Prerequisites/index.md>).
