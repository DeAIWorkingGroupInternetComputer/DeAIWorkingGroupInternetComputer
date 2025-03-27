# 2025.03.27 Meeting Summary - DeAI Working Group for the Internet Computer (ICP)

## Short Version
GPU integration remains challenging due to WASM compatibility, determinism, and VRAM limitations, making large-model GPU deployments inefficient. The current AI Worker is managed off-chain by DFINITY, communicating via polling, with no immediate scalability issues. To decentralize AI workers, two main strategies—standardized hardware setups ("Classic") and flexible hardware models with reward incentives ("Badlands")—are under discussion. A hybrid approach, gradually opening governance to additional contributors, is proposed as a practical compromise. Interest is growing around affordable, powerful hardware solutions like NVIDIA DGX Spark (~$4000). Next steps involve exploring these hybrid models, organizing open forums with ICP node providers in Q2 2025, and closely monitoring hardware advancements.

### Links shared during the call:
* https://w36hm-eqaaa-aaaal-qr76a-cai.raw.icp0.io/metrics
* https://www.nvidia.com/en-us/products/workstations/dgx-spark/
* https://www.nvidia.com/en-us/data-center/dgx-h200/

## Long Version
## Main Topics:

### 1. Current Status of GPU Integration
GPU parallelization remains challenging due to WASM compatibility and determinism requirements.

Past experiments with GPU subnets revealed issues like VRAM cost, model loading time, and efficiency concerns, especially for large LLMs.

Concluded that arbitrary large models on GPU subnets would not be efficient due to VRAM limitations and IO overhead.

### 2. Current AI Worker Architecture
AI Worker currently off-chain, managed by DFINITY, communicates with on-chain LLM canisters via polling.

Approximately 8,000 total requests processed since launch (~250/day), with no immediate scalability bottlenecks identified yet.

### 3. Decentralization Approaches
Two primary strategies discussed for decentralizing AI workers:

**Classic Approach:**
- Define standardized hardware specs.
- Node providers purchase and replicate similar setups.
- **Advantage:** Well-understood, robust trust model.
- **Disadvantage:** Expensive, inflexible, potential hardware obsolescence risk.

**Badlands Approach:**
- Flexible; diverse AI worker setups.
- Rewards distributed based on latency, uptime, and trustworthiness.
- **Advantage:** Flexibility, future-proofing, scalability.
- **Disadvantage:** Potential controversy over trust and decentralization guarantees.

### 4. Proposed Hybrid Approaches
Proposed a hybrid model where current trusted ICP node providers initially operate flexible hardware setups. This allows incremental decentralization without full openness initially.

Suggested extending this model by using governance mechanisms (e.g., SNS) to allow node providers to invite other contributors, adding governance and standardization layers.

### 5. Hardware Landscape (DGX Spark Discussion)
Discussed NVIDIA DGX Spark (cost ~$4000), as potential affordable, powerful hardware for decentralized AI nodes, capable of running and training significant LLMs.

Ritvik and Icarus (node providers) showed interest in exploring this hardware.

---

## Next Steps:
- Continue exploring hybrid decentralization models.
- Potentially organize open forums inviting more ICP node providers to discuss hardware standards, decentralization, and AI infrastructure experimentation in Q2 2025.
- Monitor evolving hardware (like DGX Spark) for feasibility as decentralized AI worker nodes.