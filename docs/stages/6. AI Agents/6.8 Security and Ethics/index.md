# 6.8 Security and Ethics

## Goal

Agents connect models to tools, files, users, databases, and sometimes money.
That makes security part of the architecture, not a final checklist.

## Roadmap.sh Topics Covered

| Group | Topics |
|---|---|
| Security | prompt injection/jailbreaks, tool sandboxing/permissioning, data privacy and PII redaction |
| Ethics | bias and toxicity guardrails, safety and red-team testing |

## Roadmap Item Notes

| Item | Beginner explanation | Agent engineering check |
|---|---|---|
| Prompt Injection / Jailbreaks | Attacks that try to override instructions, reveal secrets, or force unsafe behavior. Indirect injection can arrive through webpages, docs, emails, or tool outputs. | Treat all user and retrieved content as untrusted. |
| Tool Sandboxing / Permissioning | Tools should run with limited access, time, network, files, and credentials. | Can a compromised prompt cause the tool to do real damage? |
| Data Privacy + PII Redaction | Agents often see user data, documents, logs, and tool results. | Redact or avoid storing sensitive data unless required and consented. |
| Bias and Toxicity Guardrails | Models can produce harmful, unfair, or abusive outputs. | Test across user groups, domains, and adversarial phrasing. |
| Safety + Red Team Testing | Red teams actively try to break the system before users do. | Keep a repeatable attack set and rerun it after changes. |

## Security Layers

| Layer | What to protect |
|---|---|
| Prompt | separate trusted instructions from untrusted content |
| Retrieval | label retrieved text as untrusted evidence, not instructions |
| Tools | least privilege, sandboxing, confirmation for writes |
| Memory | avoid storing secrets, PII, or attacker instructions |
| Logs | redact secrets and private data |
| Deployment | rotate credentials, limit scopes, monitor abuse |

OWASP treats prompt injection as a core LLM application risk. For agents, the
risk grows because prompt injection can influence tool calls, memory writes, or
external actions.

## Learn

| Risk | Example defense |
|---|---|
| Prompt injection | separate trusted instructions from untrusted content |
| Tool injection | treat retrieved docs and webpages as untrusted input |
| Excess permission | least-privilege tools and scoped credentials |
| Unsafe writes | confirmation gates and human approval |
| Data leakage | PII redaction, secret scanning, log filtering |
| Bias/toxicity | policy checks, eval slices, review workflows |
| Jailbreaks | adversarial evals and refusal consistency checks |

## Build

Create a security package for your agent:

- threat model
- tool permission matrix
- prompt-injection test set
- PII handling policy
- log redaction check
- human-approval policy for risky actions
- red-team report with before/after results

## Measure

Measure:

- prompt-injection success rate
- unsafe tool-call attempts blocked
- PII leakage in logs
- false blocks
- human approval frequency
- safety regression after prompt/tool changes

## Exit Criteria

Move on when you can:

- explain prompt injection vs jailbreaks
- sandbox or permission each tool
- keep secrets and PII out of traces
- design human approval for write actions
- show security eval results before and after mitigations

## Study References

- [OWASP Top 10 for LLM Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
- [OWASP Prompt Injection](https://owasp.org/www-community/attacks/PromptInjection)
- [OWASP MCP Top 10](https://owasp.org/www-project-mcp-top-10/)
- [AI Engineering resources](https://github.com/chiphuyen/aie-book), prompt attacks and security resources

## Next

Continue to [6.9 Capstone](<../6.9 Capstone/index.md>).
