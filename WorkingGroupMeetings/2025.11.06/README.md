# 2025.11.06 Meeting Summary - DeAI Working Group for the Internet Computer (ICP)

## Short Version
The WG discussed two strong open small-LLM contenders (IBM Granite 4 & ETH Apertus) and new TEEs running on AMD SEV-SNP. Hardware advances (Zen 5 EPYC Gen 3 nodes) could bring ~50 % faster performance, but protocol-set instruction limits—not memory—remain the bottleneck for running larger models on-chain. Focus remains on hybrid architectures—canister logic + adjacent AI services—for practical DeAI growth.

### Links shared during the call:
* https://www.ibm.com/new/announcements/ibm-granite-4-0-hyper-efficient-high-performance-hybrid-models
* https://www.ibm.com/new/announcements/ibm-granite-4-0-tiny-preview-sneak-peek
* https://www.ibm.com/new/announcements/ibm-granite-iso-42001
* https://huggingface.co/blog/ibm-granite/granite-4-nano
* https://ethz.ch/en/news-and-events/eth-news/news/2025/09/press-release-apertus-a-fully-open-transparent-multilingual-language-model.html
* https://forum.dfinity.org/t/first-sev-snp-enabled-node-deployed/59499?u=icarus
* https://dashboard.internetcomputer.org/network/nodes/hckfw-kshvv-mzhew-h6isd-5q2wd-lde6w-uipmv-7gbuz-53wqz-cz5kx-oqe
* https://dashboard.internetcomputer.org/proposal/136408
* https://www.esafety.gov.au/industry/basic-online-safety-expectations

## Long Version
### Main topics: small open LLMs (IBM Granite 4, ETH Zurich Apertus), on-chain runtime limits, node hardware generations, and Trusted Execution Environments (TEEs).

### 🧠 Model & Infra Updates

* IBM Granite 4 (Nano/Tiny): new Apache-licensed family combining transformer + state-space design (Mamba-like) → large context at lower KV-cache cost; ISO 42001-aligned AI governance. Can run locally (llama.cpp, Ollama) or on Watsonx.
* ETH Zurich Apertus: recently released open LLM (DFINITY has academic ties). Both models flagged as promising for ICP/DeAI evaluations.
* Runtime ceiling: current IC protocol can practically host ≈ 1 B-param models; the hard limit stems from instruction-budget + latency, not memory alone. 7–8 B might become possible with future hardware/runtime optimizations.

### 🔒 Trusted Execution Environments (TEEs)

* First AMD SEV-SNP–based TEE nodes are live and attested. Enables encrypted memory and VM isolation on-chain with negligible performance loss.
* Rollout path: Gen 2 → Gen 3 nodes forming encrypted subnets over the next upgrade cycle.

### ⚙️ Hardware Evolution & Node Generations

* AMD vs Intel TEEs: each CPU vendor uses a distinct implementation; DFINITY’s TEE stack is built for AMD’s SEV-SNP standard, not yet portable to Intel SGX/TDX without major re-engineering.
* Gen 3 Nodes: would bring Zen 5 EPYCs (~40–50 % faster cores, DDR5/6 GHz RAM, PCIe 5.0 NVMe) and better accelerator support.
* Even so, the protocol-level instruction cap is a software constraint—so performance gains might not automatically enlarge on-chain model size.
* Testing on Gen 3 could extend practical on-chain LLMs to roughly 8–14 B parameters, but still short of true large-model inference.
* Hardware roadmap:

  * Gen 1 nodes extended +2 yrs (≈ 6-year lifecycle).
  * Gen 2 nodes (TEE-capable) remain sufficient; network currently has excess capacity, reducing incentive for Gen 3 deployment until usage surges (e.g. via Caffeine AI or DeAI apps).
  * Next-gen hardware planning will likely finalize by late 2026 → onboarding in 2027, emphasizing accelerator-ready chassis and power envelopes for GPUs or future ASICs.

### 📈 Strategic Outlook

* Near-term focus stays on adjacent AI services off-chain to augment canister workloads rather than forcing larger LLMs directly on-chain.
* Community may assist DFINITY in defining hardware specs for Gen 3 nodes (accelerator compatibility, power budgets, slot design).