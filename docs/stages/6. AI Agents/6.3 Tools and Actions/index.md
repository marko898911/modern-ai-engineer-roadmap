# 6.3 Tools and Actions

## Goal

Tools are where agents become useful and dangerous. A tool is a capability with
a name, description, schema, execution boundary, error model, and permission
policy.

## Roadmap.sh Topics Covered

| Group | Topics |
|---|---|
| Tool definition | name and description, input/output schema, error handling, usage examples |
| Example tools | web search, code execution/REPL, database queries, API requests, email/Slack/SMS, file system access |

## Roadmap Item Notes

| Item | Beginner explanation | Agent engineering check |
|---|---|---|
| Name and Description | The name is the handle the model selects; the description tells the model when and why to use it. | Could a model distinguish this tool from the others by description alone? |
| Input / Output Schema | Schemas define valid arguments and predictable results. They are the contract between model and code. | Are all required fields, enum values, limits, and output fields explicit? |
| Error Handling | Tools fail through bad inputs, timeouts, missing auth, empty results, and external service errors. | Does every error return a structured message the agent can act on? |
| Usage Examples | Examples teach the model correct tool calls and help developers test the tool. | Do examples include normal, edge, and invalid calls? |
| Web Search | Finds fresh information outside the model. | Treat results as untrusted input and require citations or source metadata. |
| Code Execution / REPL | Runs code to calculate, inspect, transform, or test. | Sandbox it, limit runtime/files/network, and never pass secrets. |
| Database Queries | Reads or writes structured data. | Prefer read-only first; use allowlisted queries or safe query builders. |
| API Requests | Calls external services. | Handle auth, rate limits, retries, idempotency, and audit logs. |
| Email / Slack / SMS | Communicates with people. | Draft first; require confirmation before sending. |
| File System Access | Reads or writes local files. | Scope directories, block sensitive paths, and log every write. |

## Tool Contract Template

```text
Name:
Purpose:
When to use:
When not to use:
Input schema:
Output schema:
Possible errors:
Permissions:
Examples:
Tests:
```

This mirrors the pattern in `building-llm-applications/ch11`, where tools are
ordinary functions with descriptions, typed inputs, and tool-call outputs that
are added back into the agent state.

## Learn

| Tool design question | Why it matters |
|---|---|
| What does the tool do? | vague tools produce vague or unsafe calls |
| What input schema is valid? | schema quality controls model behavior |
| What output schema returns? | output quality affects next loop step |
| What errors can happen? | agents need recoverable errors |
| What permissions apply? | tools should be least-privilege |
| Is it read-only or write-capable? | write tools need confirmations and logs |

## Build

Implement three tools:

1. read-only search or retrieval tool
2. read-only database or file lookup tool
3. write-capable task creation tool with confirmation

Each tool must include:

- name
- description
- JSON schema
- input validation
- structured output
- structured errors
- tests
- permission notes

## Measure

Measure:

- valid tool-call rate
- invalid argument rate
- tool error recovery
- latency
- false-positive write attempts
- whether unsafe inputs are rejected

## Exit Criteria

Move on when you can:

- design tool schemas that are small and precise
- explain read vs write tool risk
- return errors the agent can recover from
- test tools without the LLM
- log tool calls without leaking secrets

## Study References

- [OpenAI function calling](https://platform.openai.com/docs/guides/function-calling)
- [OpenAI structured outputs](https://platform.openai.com/docs/guides/structured-outputs)
- `building-llm-applications/ch11/main_02_02.py` for binding tools and executing tool calls
- [AI Engineering resources](https://github.com/chiphuyen/aie-book), Chapter 6 resources on tools and agent failure modes

## Next

Continue to [6.4 Agent Memory](<../6.4 Agent Memory/index.md>).
