# 2025.05.08 Meeting Summary - DeAI Working Group for the Internet Computer (ICP)

## Short Version
Wyatt gave an update on Kinic’s browser plugin which is now in open beta and then deep dived into Zero-Knowledge Machine Learning (ZKML). His presentation explored ZKML on the Internet Computer (ICP), highlighting how zk-proofs enable verifiable AI computation without exposing sensitive data. He compared ZK with Trusted Execution Environments (TEEs), outlined technical advancements like folding schemes, Jolt-based ZKVMs, and WebGPU acceleration, and showcased real-world use cases such as private LLM inference and AI agent coordination. The ICP's architecture allows for native on-chain verification of modern proof systems, positioning it as a powerful platform for decentralized, privacy-preserving AI.

### Links shared during the call:
* https://www.kinic.io/ 
* https://www.novanet.xyz/ 
* Fun demos we do of our zkTech https://zkp.fun/ 
* Research refs: https://eprint.iacr.org/2023/1217 
*  https://eprint.iacr.org/2021/370 
* Older work which is still interesting: https://arxiv.org/abs/2404.16109 
* Starter ZK: zkHack Discord https://discord.gg/Aq7VvtHN 
* Thaler's book. He also does session above: https://people.cs.georgetown.edu/jthaler/ProofsArgsAndZK.pdf

## Long Version
# Zero-Knowledge ML on ICP

## 🎤 Main Presentation: Wyatt on ZKML
Wyatt gave a deep dive into zero-knowledge machine learning (ZKML), its implications for decentralized compute, and the architectural superpowers of the Internet Computer (IC) for zk-proofs. He explored how AI workloads can be verified without exposing sensitive data, enabling trustless computation.

---

## 🔍 Key Topics Discussed

### 🔧 Kinic Updates
- **Kinic Plugin**: Now in open beta. Allows users to spin up a vector DB on IC, deployable via OpenChat + Connect wallet. Stripe integration coming.
- **Use Case**: Local context-aware AI for querying private data (e.g., email, bookmarks) without exposing it to Web2 platforms.

### 🔒 Verifiable AI: ZK vs TEEs
- Most AI verifiability today uses Trusted Execution Environments (TEEs) (e.g., SGX), but these are:
  - Expensive and fragile (attack surface, supply chain risks).
  - Not privacy-preserving by default.
- TEEs already use ZK to compress attestation proofs.
- ZKPs (Zero-Knowledge Proofs) offer a cryptographic alternative, with rapid performance gains (100x in past year).

### 🧠 ZKML & Folding Schemes
- ZKML = applying ZK to ML inference (e.g., proving an iris scan or model output without revealing inputs).
- Popular misconception: ZKML is too slow or memory-hungry. New schemes (e.g., Folding, Nova, Supernova, Hypernova) challenge that.
- Folding enables incremental verifiable computation (IVC) with minimal memory growth.
- NovaNet coordinates distributed provers to parallelize proving across machines.

### 📚 Technical Advances
- Lookup arguments and smarter math (e.g., GKR protocols) reduce circuit complexity.
- Jolt (from a16z) is a blazing-fast ZKVM using lookup-only logic; being modified to support floating point ops for ONNX-based ZKML.
- Smaller models + smaller circuits = practical ZKML on WebGPU and in-browser.

### ✅ ZK for Privacy, Not Just Scaling
- ZKPs are now being adopted beyond Ethereum scalability — including privacy-preserving compute.
- Wyatt emphasized: "Don’t hold the data, prove the computation."
- Avoids legal and infrastructural burden (e.g., GDPR) by keeping user data off-chain and proving only outcomes.

---

## 🧰 Infrastructure Highlights
- **IC advantage**: most modern ZKPs can be verified directly on-chain, no need to downscale proofs (unlike Ethereum).
- Provers still too memory-intensive to run directly in IC canisters but can run locally and post verifiable outputs.
- IC can verify modern proof systems like Groth16, STARKs, and Jolt-based proofs without months of engineering effort.

---

## 🧠 ZKML Proof Flow
- Models are converted from ONNX → executed in a modified ZKVM → memory & execution traces are generated → these are proven.
- For devs: like running a normal ONNX model, but behind the scenes it creates verifiable cryptographic proofs.

---

## 🖥️ Hardware Considerations
- ZKP provers benefit from GPU acceleration, especially for elliptic curve operations (MSM).
- WebGPU support enabled browser-based proofs at significantly reduced time (e.g., 2 minutes → 9 seconds).
- TEEs often lack GPU support, making them less suitable for complex AI workloads.

---

## ⚖️ TEEs vs ZK Proofs
- TEEs provide isolation, not verifiability.
- ZKPs provide mathematical guarantees without needing to trust hardware vendors or jurisdictions.
- TEEs can still be useful in hybrid models, but don’t guarantee correctness of AI model execution.

---

## 🧪 Real-World ZKML Use Cases
- Fine-tuned LLMs or private datasets can remain confidential while proving that outputs came from authentic computation.
- Example: predicting BTC price using private data + public model → prove accuracy without revealing data.
- Governments or financial institutions could leverage this for auditability.

---

## 🔁 AI Agent Interactions & ZK

### Use Cases
- Scheduling meetings via agents without exposing personal calendar data.
- Playing fair multi-agent games (e.g., poker) with private strategies, verified post-hoc.
- ZK-enabling value exchange between autonomous agents (AI-to-AI economy).

### Critical Insight
- AI agent compute may happen off-chain, but interaction with IC ensures trust, resilience, and proof anchoring.

---

## 🛠️ ZKML Tooling Updates
- ZKVM pipeline supports ONNX models directly.
- Memory-heavy operations (e.g., memory access consistency) are automatically included in the proof.
- Jolt and DeepProve support improving performance.

### Performance Benchmarks
- A recent paper ran full LLM inference (state-of-the-art model) in ~10 minutes on one machine.
- With parallelization: expect <30s latency for many workloads.
- Browser-native proof generation (via WebGPU) will enable fun ZKML competitions ("proof parties").

---

## 🧞 Wishlist for IC Ecosystem
- **Wasm64** support to enable heavier compute and direct prover execution in canisters.
- More exploration of ZKML within DFINITY, which historically focused on alternative cryptography.
- IC’s ZK narrative should evolve beyond TEEs to resonate with Web3 (e.g., "ZKML on-chain").

---

## 📅 Outlook & Next Sessions
- **Next week**: Call on MCP (Multi-Canister Protocol) and Google’s Agent-to-Agent (A2A) protocol.
- **In two weeks**: Icarus presents on accelerated AI infrastructure for ICP.
- Time changes to accommodate Asia-Pacific contributors.

---

## 🧾 Summary Thought
ZKML on ICP represents a promising shift: AI agents and models can operate privately, verifiably, and autonomously — unlocking an entirely new dimension of decentralized trust.

---

## 🗓 Upcoming Calls & Topics

| Date     | Topic                                                                                                 | Presenter     |
|----------|-------------------------------------------------------------------------------------------------------|---------------|
| May 15     | MCP & Agent2Agent Protocol |    @baolongt      |
| May 22     | AI4AI |     @icarus     |
| May (tbd)| Session on Efficient LLMs and DeepSeek                                                               |               |
| May (tbd)| Session on instruction limit                                                                          |               |
| Future   | Expert session on Active Inference implementations                                                    | Invite TBD    |
