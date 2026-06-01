# Old Roadmap Analysis

This page captures the analysis of `ai-hardware-engineer-roadmap` so the new
roadmap can keep what works and avoid repeating the confusing parts.

## What Works Well

| Strength | Keep it? | How this roadmap uses it |
|---|---|---|
| Clear ambition | Yes | Keep a bold endpoint, but define smaller milestones first |
| MkDocs Material site | Yes | Reuse the same deployable documentation style |
| Build-and-measure culture | Yes | Every stage has artifacts and metrics |
| Inference and hardware depth | Yes | Move it to Stage 8 after LLM/system basics |
| Role awareness | Yes | Put roles in a separate Tracks page |
| Projects | Yes | Make projects the learning backbone |

## What Makes It Hard for Beginners

| Problem | Why it hurts | Correction |
|---|---|---|
| Too many nested folders | Learners cannot see the whole path | Keep one `stages/` directory and one `tracks/` page |
| Endpoint is too specialized | Chip design overwhelms general AI learners | Make modern AI engineer the base; hardware is a specialist depth |
| Tracks start too early | Beginners do not know what to choose | Main path first, tracks later |
| Agent content mixed with hardware story | Agent learning gets buried | Make agents their own stage |
| No beginner on-ramp | Student cannot tell what to do in week 1 | Add Stage 0, Stage 1, and first 30 days guidance |
| Advanced topics feel equally required | Everything looks mandatory | Mark required vs important vs optional |
| Learning material and roadmap blur together | It becomes a course archive, not a path | Roadmap pages stay short; resources and projects live separately |

## Design Principle for the New Roadmap

The old roadmap asks:

```text
How do I become someone who can design AI hardware?
```

The new roadmap asks:

```text
How do I become a modern AI engineer from beginner to master?
```

That broader goal changes the structure. Hardware acceleration still matters,
but only after the learner understands AI workloads, LLM behavior, production
systems, and measurement.

## New Information Architecture

```text
Home
|-- How to Use
|-- Roadmap Map
|-- Stages
|   |-- 0 Orientation
|   |-- 1 Foundations
|   |-- 2 Machine Learning
|   |-- 3 Deep Learning
|   |-- 4 LLMs
|   |-- 5 AI Applications
|   |-- 6 AI Agents
|   |-- 7 Model Infrastructure
|   |-- 8 Optimization and Hardware
|   |-- 9 Security, Blockchain, ZKML
|   `-- 10 Mastery
|-- Tracks
|-- Projects
`-- Resources
```

## The Correction

This roadmap will be successful if a beginner can answer these questions after
ten minutes:

- Where do I start?
- What should I build first?
- When do I learn agents?
- When do I learn infrastructure?
- When do I learn hardware acceleration?
- Where do blockchain and ZKML fit?
- How do I know I am ready to move on?

That is the real test.
