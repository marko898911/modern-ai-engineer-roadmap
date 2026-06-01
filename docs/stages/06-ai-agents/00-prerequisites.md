# 6.0 Prerequisites

## Goal

Before building agents, make sure you can build the software an agent will
operate through: backend endpoints, command-line tools, Git workflows, and REST
APIs. Agents are only useful when they can safely touch real systems.

## Roadmap.sh Topics Covered

| Roadmap topic | What it means here |
|---|---|
| Basic Backend Development | expose useful operations through HTTP or CLI |
| Git and Terminal Usage | inspect, change, run, and version projects safely |
| REST API Knowledge | understand requests, responses, auth, errors, and rate limits |
| Backend Beginner Roadmap | optional catch-up path |
| Git and GitHub Roadmap | optional catch-up path |
| API Design Roadmap | optional catch-up path |

## Roadmap Item Notes

| Item | Beginner explanation | Agent engineering check |
|---|---|---|
| Basic Backend Development | An agent needs services to call. Backend basics teach you how to turn useful work into endpoints, jobs, and functions. | Can you expose one useful action as an API and return structured errors? |
| Git and Terminal Usage | Many agents inspect files, run commands, or work inside repositories. You need to understand these operations before allowing a model near them. | Can you predict what a command or Git operation will change before running it? |
| REST API Knowledge | Tool calls are often API calls with JSON inputs and outputs. Good API habits become good tool habits. | Can your tool distinguish invalid input, missing auth, rate limits, and server errors? |
| Backend Beginner Roadmap | Use this only if APIs, routing, or server basics feel unfamiliar. | Build a tiny local service before building an agent. |
| Git and GitHub Roadmap | Use this if `clone`, `branch`, `commit`, `diff`, or pull requests are shaky. | Agents that edit code need clean diffs and rollback habits. |
| API Design Roadmap | Use this when your tools start becoming public or shared by multiple agents/apps. | Tool APIs should be narrow, typed, documented, and versioned. |

## Why This Comes First

From the agent examples in `building-llm-applications/ch11`, tools are normal
Python functions or external services wrapped in a schema. The model does not
magically understand your system. You make your system understandable by giving
it small, reliable, well-described interfaces.

## Learn

| Area | Minimum depth |
|---|---|
| HTTP | methods, status codes, headers, JSON payloads |
| APIs | endpoint design, validation, auth, pagination, rate limits |
| CLI | arguments, environment variables, exit codes, logs |
| Git | branch, diff, commit, restore, merge, pull request basics |
| Backend | FastAPI, Flask, Express, or similar |
| Safety | secrets, permissions, input validation, audit logs |

## Build

Build a small tool server:

- `GET /health`
- `POST /search-notes`
- `POST /summarize-text`
- `POST /create-task`
- structured JSON errors
- request logging
- simple API key or local-only permission check

## Measure

Measure:

- endpoint latency
- valid vs invalid request behavior
- error messages
- test coverage for each endpoint
- whether secrets appear in logs

## Exit Criteria

Move on when you can:

- call your API with `curl`
- explain each status code your API returns
- write a small command-line wrapper for one endpoint
- add validation for malformed inputs
- keep API keys and secrets out of Git and logs

## Study References

- [roadmap.sh Backend Beginner Roadmap](https://roadmap.sh/backend?r=backend-beginner)
- [roadmap.sh Git and GitHub Roadmap](https://roadmap.sh/git-github?r=git-github-beginner)
- [roadmap.sh API Design Roadmap](https://roadmap.sh/api-design)
- `building-llm-applications/ch11/main_02_02.py` for tools wrapped around retrieval and weather functions

## Next

Continue to [6.1 LLM Fundamentals](01-llm-fundamentals.md).
