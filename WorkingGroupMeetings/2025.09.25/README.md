# 2025.09.25 Meeting Summary - DeAI Working Group for the Internet Computer (ICP)

## Short Version
This session explored a new perspective on determinism in LLM inference, highlighting that non-determinism stems primarily from batching rather than GPU floating-point math. The group discussed how enforcing deterministic batching could make LLM outputs consensus-safe for decentralized systems like the Internet Computer (IC), albeit at a performance trade-off. Determinism was connected to proofs of execution, zero-knowledge ML (ZKML), and trust layers for agent-to-agent interactions, with concrete implications for DeFi, regulated domains, and privacy-preserving use cases. The conversation also touched on practical verification strategies (hashes, black hole canisters, ZK proofs), the role of temperature in inference, and the IC’s unique advantages over TEE-based approaches, setting the stage for further exploration of standardized proof layers and asynchronous, verifiable AI agents.

### Links shared during the call:
* https://github.com/thinking-machines-lab/batch_invariant_ops
* https://thinkingmachines.ai/blog/defeating-nondeterminism-in-llm-inference/

## Long Version
# Topic: Determinism in LLM inference, proofs of execution, and implications for the Internet Computer (IC)

Based on: Discussion of a recent paper reframing sources of non-determinism: [https://thinkingmachines.ai/blog/defeating-nondeterminism-in-llm-inference/](https://thinkingmachines.ai/blog/defeating-nondeterminism-in-llm-inference/)

## Core Problem: Determinism in LLM Inference

* Single inference (batch=1) is deterministic across CPUs/GPUs/TPUs.
* Non-determinism emerges in batching: parallel execution mixes request order and reductions across cores/SMs.
* Paper’s contribution: identifies batching as the primary culprit, not GPU floating-point math.
* Proposed fixes:

  * Keep batches “together” (data-parallel constraints).
  * Enforce exclusive device use during critical ops (matmul, attention).
  * Trade-off: ~20% throughput hit for deterministic outcomes.
  * Relevant to consensus systems like ICP: determinism can be guaranteed by serializing requests (batch=1), fitting asynchronous/agent workloads.

## Implications for the Internet Computer

* Canister level: IC canisters run single-threaded WASM on CPUs, already deterministic.
* System level: GPU workers (off-chain or subnets) could adopt the paper’s deterministic batching fixes.
* Use cases:

  * DeFi/Oracles: deterministic agent decisions with verifiable audit trails.
  * Regulated domains (healthcare, legal): repeatability and non-repudiation.
  * ZKML: determinism is a prerequisite for verifiable inference proofs.

## Proofs of Execution & ZKML

* Value of determinism: enables proofs of execution beyond just inputs/outputs → model, parameters, environment.
* ZKP goals:

  * Succinct verifiability (e.g., heavy computation can be verified on-chain or on mobile).
  * Polynomial encoding of computation trace + memory steps (via ONNX pipelines), enabling lightweight verification.
* Current state:

  * Deterministic inference → 5–20 minutes for small LLMs in ZK (100k× slower than raw inference).
  * Practical today for simple classification or smaller SLMs (<10s verification).
  * Still asynchronous / backend-oriented workloads.

## Determinism and Temperature

* Temperature = randomness in token sampling.
* At T=0: model always picks top token → fully deterministic chain.
* At T>0: sampling introduces randomness, but determinism could still be forced with a fixed random seed + reset per inference.
* Implication: use cases requiring determinism (finance, filtering, audits) will likely run at T=0.

## Agent-to-Agent & Trust Layers

* Determinism alone is not enough → agents and tools can be poisoned.
* Strategies raised:

  * Logging & tracing through workflows.
  * Batching responses to bound non-determinism.
  * Sandboxing agents in canisters for safer MCP tool use.
  * Assigning trust scores to tools/agents.
* Black hole canisters: a way to freeze agent code/config and provide verifiable proofs (hashes of WASM, model, settings, input, output).

## Broader Ecosystem Context

* Many Web3 “AI on blockchain” projects today rely on TEEs with attestation proofs.
* Fast, but centralized, costly (~$40k+ GPU TEEs), and not truly on-chain.
* IC advantage:

  * Can run ZK verifiers directly in canisters (no need to down-compile proofs into Groth16 or other restrictive schemes).
  * Stronger auditability, cheaper on-chain logging, and asynchronous model fits well.

## Open Questions & Next Steps

* Impact of batching non-determinism on quantized models (unclear).
* How to standardize proof-of-execution layers for IC LLM agents (hashes, audit logs, black hole canisters).
* Mapping which use cases demand strict determinism (finance, privacy, filtering) vs. which can tolerate non-determinism.
* Building a spectrum of risk-mitigation strategies: from sandboxing to ZK proofs.

## Closing & Next Call

* This discussion started from a single paper but expanded to IC-specific architectures, agent security, and ZKML integration.
* Session on Oct 9: GianM will showcase his latest work on the ICP Coder Motoko AI assistant