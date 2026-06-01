# Sources and Study Notes

This roadmap was structured from local study material, the uploaded AI Agents
PDF, and current public documentation. The goal is not to copy any one source,
but to combine their strongest ideas into a beginner-readable path.

## Local Repositories Studied

| Source | Used for |
|---|---|
| [ai-hpc/ai-hardware-engineer-roadmap](https://github.com/ai-hpc/ai-hardware-engineer-roadmap) | MkDocs/GitHub Pages pattern, hardware and inference scope, and lessons on what became too complex |
| [chiphuyen/aie-book](https://github.com/chiphuyen/aie-book) | AI engineering stack, evaluation, RAG, agents, fine-tuning, datasets, inference optimization, architecture |
| [HandsOnLLM/Hands-On-Large-Language-Models](https://github.com/HandsOnLLM/Hands-On-Large-Language-Models) | LLM fundamentals, tokenization, embeddings, transformers, RAG, multimodal, quantization, agents |
| [PacktPublishing/LLM-Engineers-Handbook](https://github.com/PacktPublishing/LLM-Engineers-Handbook) | Production LLM pipeline structure, data generation, RAG, training, deployment, monitoring |
| [roberto-inf/building-llm-applications](https://github.com/roberto-inf/building-llm-applications) | LangChain-style LLM application examples and RAG workflows |
| Uploaded `ai-agents.pdf` | Agent roadmap topics: prerequisites, prompt engineering, tools, MCP, memory, architectures, frameworks, evals, observability, security |

## Current Public References

| Area | Reference |
|---|---|
| Agent roadmap | [roadmap.sh AI Agents](https://roadmap.sh/ai-agents) |
| MCP | [Model Context Protocol documentation](https://modelcontextprotocol.io/docs) |
| Agents SDK | [OpenAI Agents guide](https://platform.openai.com/docs/guides/agents) and [OpenAI Agents SDK](https://openai.github.io/openai-agents-python/) |
| LLM/deep learning learning path | [Hugging Face LLM Course](https://huggingface.co/learn/llm-course), [PyTorch Tutorials](https://docs.pytorch.org/tutorials/), [Dive into Deep Learning](https://d2l.ai/) |
| ML fundamentals | [Stanford CS229](https://cs229.stanford.edu/) |
| Serving and inference | [vLLM documentation](https://docs.vllm.ai/), [SGLang documentation](https://docs.sglang.ai/), [NVIDIA TensorRT-LLM](https://nvidia.github.io/TensorRT-LLM/), [NVIDIA Triton Inference Server](https://docs.nvidia.com/deeplearning/triton-inference-server/user-guide/docs/) |
| AI security | [OWASP Top 10 for LLM Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/), [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework), [MITRE ATLAS](https://atlas.mitre.org/) |
| ZK and ZKML | [ezkl documentation](https://docs.ezkl.xyz/), [RISC Zero documentation](https://dev.risczero.com/), [Succinct SP1 documentation](https://docs.succinct.xyz/), [Circom documentation](https://docs.circom.io/), [The Halo2 Book](https://zcash.github.io/halo2/) |

## How Sources Influenced Structure

| Source idea | Roadmap decision |
|---|---|
| AI Engineering emphasizes evaluation, feedback, and architecture | Evaluation appears before agents and infrastructure, not after |
| Hands-On LLMs is visual and concept-first | LLMs get their own fundamentals stage before RAG/agents |
| LLM Engineer's Handbook uses production pipelines | Model infrastructure is a full stage, not a footnote |
| The AI agents PDF is broad but practical | Stage 6 keeps all agent topics, but puts them in build order |
| AI hardware roadmap is rich but too nested | This roadmap uses flat stages, role tracks, and project artifacts |
| Current inference docs are engine-specific | Stage 8 teaches metrics and bottlenecks before choosing tools |
| OWASP/NIST/MITRE make security explicit | Security is not only a final checklist; it appears in apps, agents, and Stage 9 |
| ZKML tooling is powerful but constrained | ZKML is treated as specialist verification work, not a general serving path |

## Update Policy

Review this page at least quarterly. Fast-moving areas:

- model families
- agent frameworks
- MCP ecosystem
- serving engines
- quantization formats
- AI security threats
- ZKML tooling and proof performance
