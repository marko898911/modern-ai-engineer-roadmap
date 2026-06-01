<div align="center">
  <img src="docs/assets/images/avatar.png" alt="Modern AI Engineer Roadmap avatar" width="160">
</div>

# Modern AI Engineer Roadmap

Beginner-to-master roadmap for becoming a modern AI engineer: AI and ML
fundamentals, deep learning, LLMs, RAG, agents, model infrastructure,
optimization, hardware acceleration, AI security, blockchain, and ZKML.

The live site is intended for GitHub Pages:

https://aiZKP.github.io/modern-ai-engineer-roadmap/

## What Makes This Roadmap Different

This roadmap is designed to be walked, not admired from far away.

- It starts from beginner assumptions.
- It separates required foundations from specialist tracks.
- Every stage has a concrete build artifact and exit criteria.
- Advanced topics like agents, serving, CUDA, security, blockchain, and ZKML
  appear only after the learner has enough context to use them.
- The structure stays flat enough that a student can always answer:
  "Where am I, what comes next, and what should I build?"

## Project Structure

```text
modern-ai-engineer-roadmap/
|-- README.md
|-- mkdocs.yml
|-- requirements.txt
|-- docs/
|   |-- index.md
|   |-- how-to-use.md
|   |-- roadmap-map.md
|   |-- stages/
|   |-- tracks/
|   |-- projects/
|   |-- resources/
|   |-- meta/
|   `-- assets/
`-- .github/workflows/deploy-docs.yml
```

## Local Preview

```bash
python -m pip install -r requirements.txt
mkdocs serve
```

Then open `http://127.0.0.1:8000/modern-ai-engineer-roadmap/`.
