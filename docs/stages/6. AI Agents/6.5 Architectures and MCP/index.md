# 6.5 Agent Architectures and MCP

## Goal

Agent architecture decides how tasks are decomposed, how tools are chosen, how
state moves, and how failures are controlled. Start with simple architectures
and add complexity only when the evals demand it.

## Roadmap.sh Topics Covered

| Group | Topics |
|---|---|
| Common architectures | ReAct, Chain of Thought, RAG agent, planner-executor, DAG agents, Tree-of-Thought |
| Additional patterns | self-critique agents, multi-agents |
| MCP | Model Context Protocol, hosts, clients, servers, creating MCP servers, local desktop and remote/cloud deployment |

## Roadmap Item Notes

| Item | Beginner explanation | Agent engineering check |
|---|---|---|
| ReAct | The model alternates between reasoning about what to do and acting through tools. | Are reasoning traces useful for debugging, or are they noisy and expensive? |
| Chain of Thought | The model performs intermediate reasoning before answering. | Prefer private reasoning or structured plans; do not depend on hidden thoughts as logs. |
| RAG Agent | Retrieval is treated as a tool inside a broader agent loop. | Can the agent decide when retrieval is needed and detect weak retrieval? |
| Planner Executor | One component makes a plan; another executes steps. | Can the executor recover when the plan is wrong? |
| DAG Agents | Work is represented as graph nodes with controlled transitions. | Good for production because states and transitions are inspectable. |
| Tree-of-Thought | The agent explores multiple solution paths. | Useful for hard reasoning, but expensive and usually unnecessary for simple workflows. |
| Self-critique Agents | The model reviews or revises its own output. | Helpful for drafts, risky if critique is treated as proof. |
| Multi-Agents | Multiple agents cooperate with roles. | Add only after one-agent evals show a role split is necessary. |
| Model Context Protocol | MCP standardizes how applications expose tools, resources, and prompts to model clients. | Know which server exposes which capability and with what permission. |
| MCP Hosts | Applications that users interact with, such as an IDE or desktop app. | The host controls user experience and consent. |
| MCP Client | The connector inside the host that talks to MCP servers. | The client manages protocol communication and capability discovery. |
| MCP Servers | Programs that expose tools, resources, or prompts. | Servers must validate inputs and protect secrets. |
| Creating MCP Servers | Build a small server that exposes one safe tool or resource. | Start local and read-only before remote or write-capable. |
| Local Desktop | MCP server runs on the user's machine. | Easier for local files, but permissions are very sensitive. |
| Remote / Cloud | MCP server runs as a network service. | Requires auth, tenancy, rate limits, and monitoring. |

## Architecture Choice Rule

Start with the simplest loop that can pass the eval. Move to planner-executor,
DAG, or multi-agent patterns only when you can name the failure mode the extra
architecture fixes.

## Learn

| Architecture | Good for | Risk |
|---|---|---|
| ReAct | interleaving reasoning and tool use | noisy traces and overthinking |
| RAG agent | grounded answers from external knowledge | retrieval failure mistaken as reasoning failure |
| Planner-executor | multi-step tasks | brittle plans if environment changes |
| DAG agent | predictable workflows with model decisions inside nodes | less flexible |
| Tree-of-Thought | exploring multiple possible solutions | expensive and slow |
| Self-critique | review and correction | false confidence |
| Multi-agent | role separation | coordination overhead |
| MCP | standardized external tool/context integration | permission and deployment complexity |

## Build

Create an architecture comparison:

- implement the same task as ReAct
- implement it as planner-executor
- implement it as a simple DAG
- sketch how an MCP server would expose one tool

## Measure

Measure:

- task success
- number of model calls
- number of tool calls
- latency
- cost
- failure interpretability
- ease of adding a new tool

## Exit Criteria

Move on when you can:

- choose the simplest architecture for a task
- explain MCP host/client/server roles
- describe local vs remote MCP deployment tradeoffs
- explain when multi-agent design is justified
- compare architecture choices using measurements

## Study References

- [Model Context Protocol docs](https://modelcontextprotocol.io/docs)
- [MCP resources](https://modelcontextprotocol.io/docs/concepts/resources)
- [MCP prompts](https://modelcontextprotocol.io/docs/concepts/prompts)
- `building-llm-applications/ch11/main_07_01.py` for an MCP-flavored tool integration example
- [Hands-On LLMs agent bonus](https://github.com/HandsOnLLM/Hands-On-Large-Language-Models/blob/main/bonus/9_agents.md)

## Next

Continue to [6.6 Building Agents](<../6.6 Building Agents/index.md>).
