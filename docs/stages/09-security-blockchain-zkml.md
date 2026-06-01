# Stage 9: AI Security, Blockchain, and ZKML

<span class="stage-badge">9</span> Secure AI systems, understand blockchain security, and learn how ML can be verified with cryptographic proofs.

## Goal

AI security is not a side topic. Modern AI systems call tools, read private
data, generate code, influence decisions, and may interact with smart contracts.
This stage joins three areas:

- LLM and agent security
- blockchain and smart contract security
- ZKML and verifiable computation

## Learn

| Area | What to understand |
|---|---|
| LLM security | prompt injection, jailbreaks, data leakage, unsafe outputs |
| Agent security | tool permissions, sandboxing, secret handling, audit logs |
| AI governance | NIST AI RMF, risk mapping, evaluation, monitoring |
| AppSec basics | auth, secrets, supply chain, dependency scanning, threat modeling |
| Blockchain basics | wallets, signatures, transactions, gas, smart contract execution |
| Smart contract security | reentrancy, access control, oracle risk, MEV, upgrade risk |
| ZK fundamentals | commitments, circuits, witnesses, proving, verifying |
| zkVMs | prove program execution instead of hand-writing every circuit |
| ZKML | prove facts about model inference or model-related computation |

## Build

Build three artifacts:

1. Threat model for your Stage 6 agent.
2. Smart contract security lab with at least 3 vulnerabilities and fixes.
3. Tiny ZKML demo proving a small model inference or threshold decision.

## Measure

Measure:

- number of security tests
- attack success rate before and after mitigations
- proof generation time
- verifier time or gas if on-chain
- model size limits
- precision/quantization impact on proof feasibility

## Exit Criteria

Move on when you can:

- explain prompt injection and tool injection with examples
- design least-privilege tool access for an agent
- write a basic AI system threat model
- audit simple smart contract risks
- explain what a ZK proof proves and what it does not prove
- build a tiny ZKML proof and describe its limits

## ZKML Learning Order

1. Learn basic cryptographic vocabulary.
2. Write small circuits or use a simple proving framework.
3. Understand fixed-point arithmetic and quantization.
4. Export a tiny model to ONNX or equivalent representation.
5. Generate a proof for a tiny inference.
6. Verify locally.
7. Explore on-chain verification only after local proof works.

## Important Warning

ZKML is young and constrained. Treat it as a specialist capability for
verification, privacy, and trust, not as a replacement for normal model serving.

## Next

Continue to [Stage 10: Mastery](10-mastery.md).
