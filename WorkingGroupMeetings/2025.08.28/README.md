# 2025.08.28 Meeting Summary - DeAI Working Group for the Internet Computer (ICP)

## Short Version
The call covered three main threads: first, experiments with alternative AI hardware showed current custom setups struggle to match NVIDIA’s performance, though FPGA-based startups like Positron AI offer interesting reprogrammable options; second, privacy and trust remain major risks in centralized AI (e.g., log retention, model substitution), with TEEs and IC-local execution seen as credible paths to provable confidentiality; third, discussion turned to architecture, where the group explored integrating confidential GPU-backed VMs directly into ICP subnets via consensus-driven deployment and VSOC connections, though the key open question remains whether the added security and decentralization benefits justify the cost and complexity compared to simply using external APIs.

### Links shared during the call:
* https://www.positron.ai/
* https://github.com/tenstorrent/tt-metal/issues?q=is%3Aissue%20state%3Aopen%20label%3Ablackhole

## Long Version
# 🔧 Hardware & Model Performance Discussion

### Temperature Effects on Throughput:
- At temp=0, throughput reached 42 tokens/sec on dual cards.  
- Increasing temperature drastically reduced throughput: 34 tokens/sec at mid-range, 16 tokens/sec at temp=1.  
- Optimizations pushed temp=1 back up to ~29–30 tokens/sec, but still short of the ~50+ tokens/sec needed for smooth production-grade inference.  

### Power & Efficiency Trade-offs:
- Each card drew ~300W (dual setup ~600W).  
- Custom chip approaches (vs. NVIDIA) offer more control/privacy but often lack efficiency.  
- Some Llama/Mistral forks don’t run well on NVIDIA, making custom cards more attractive despite lower perf/watt.  

### TensTorrent & Software Optimization:
- Models ran but sometimes produced gibberish without Python-level adjustments.  
- Optimization efforts targeted temperature-handling code (moving compute onto the card).  
- Contributor noted desire to upstream fixes to improve open-source stack.  
- Still early days: current 30 tokens/sec isn’t competitive with NVIDIA’s H200/B200 line.  

---

# 🚀 Alternative Hardware Startups

### Positron AI (FPGA-based)
- Uses Intel Agilex 7 FPGA cards with HBM2A (32 GB).  
- Key innovation: runs Hugging Face transformer binaries directly, no custom stack or compilation layer.  
- Results: promising perf/watt and perf/$ numbers compared to NVIDIA H100 (at FP16).  
- Pricing: ~$175K for full 8-card server, ~$18K per card (not yet sold individually by default).  
- Advantage: FPGA reprogrammability → potential longer lifecycle and upgradability.  
- Risk: startup longevity and efficiency trade-offs compared to GPUs.  

### General Observations:
- Startups face steep challenge to “catch up” with NVIDIA’s pace.  
- Success likely requires architectural edge (not just cost reduction).  
- Inference-only specialization (instead of training) is emerging as a promising design path.  

---

# 🌐 LLM Canisters & IC Integration

### AI Worker & LLM Canister Context:
- Previous “AI worker” proof-of-concept (single server running LLM stack) likely being phased out.  
- Motivation: high cost to maintain and redundancy after new IC features.  

### Non-replicated HTTP Out Calls:
- Implemented to allow efficient external API calls from canisters.  
- Instead of 13 replicated calls (wasteful + inconsistent with temp/randomness), only one node sends, result is shared to reach consensus.  
- Enables LLM canisters to call OpenAI, Anthropic, etc. APIs in a cost-effective way.  
- Trade-off: loses security/decentralization guarantees; back to depending on external providers.  

### Remaining Gap:
- Without scalable on-chain AI, there’s still no secure, private, decentralized inference option beyond very limited on-chain compute.  
- Group recognized we are “back where we started, but with more knowledge of the trade-offs.”  

---

# 🔒 Privacy & Centralized AI Risks

### Compliance Certificates ≠ Privacy:
- Certifications (SOC2, ISO, etc.) often don’t prevent DevOps staff or authorities from accessing logs.  
- Logs may be cached (e.g., 30 days) and are accessible under law enforcement requests.  
- High-risk sectors like law, finance, healthcare face real vulnerabilities when prompts/contracts end up stored in provider systems.  

### Model Substitution Risk:
- One participant observed a provider advertising Llama 405B but silently downgrading queries to Llama 70B while relabeling API responses.  
- Centralized providers can relabel, reroute, and downgrade service without transparency → violates “zero trust” principles.  

### Government Log Retention Laws (Case: Australia):
- ISPs must retain logs of all traffic (residential & datacenter).  
- Under anti-terror laws, ISPs must also proactively log & track specific IPs if required by police.  
- Implication: even encrypted AI traffic routed externally can be logged and potentially decrypted in the future.  

---

# 🛡 Trusted Execution & Private Compute

### TEE-based Guarantees (Intel SGX, AMD SEV):
- Since 2021, newer CPUs support chip-level encryption for isolated enclaves.  
- Workflow: request encrypted → logged by ISP → decrypted only inside a verified enclave → host operator cannot inspect.  
- Keys released only via attestation broker → ensures code+environment integrity before execution.  
- Extends to AI inference: users encrypt inputs, enclave decrypts & runs model securely.  

### Next-Gen Concepts:
- Research into encrypted data at GPU-level (homomorphic-like inference) → would avoid private-compute intermediaries, but degrades performance.  
- Apple Private Compute mentioned, but seen as white-paper level, not fully deployed.  

---

# 🌍 Market & Value Considerations

### Do Users Care About Privacy?
- General consumers: usually not (Google/Facebook precedent).  
- Sensitive domains: legal, finance, therapy/medical → demand strong confidentiality + auditability.  
- Example: “AI as therapist” → huge privacy stakes, but users often trust blindly due to knowledge gap.  

### European Context:
- EU subnets / Swiss subnets on ICP → enforce data locality (e.g., data doesn’t leave Europe).  
- EU market seen as more privacy-sensitive vs. US/China, but enforcement is law-driven, not provider-driven.  

### Auditability & Proof:
- Value proposition shifts from “trust big providers” to provable guarantees:  
  - Secure attestation  
  - Open-source software stacks  
  - Immutable audit logs on-chain  
- Customers want proof > promises (contrast with AWS/Google/Microsoft “trust us” model).  

---

# ⚡ Developer & User Experience

### ICP Advantage: Cycles Model
- Transparent, frictionless accounting for compute.  
- If extended to AI compute (per-token charging) → no credit cards, no API setup → just cycles.  
- Creates smooth dev-to-prod pipeline: idea → running app with AI in minutes.  
- Easy integration with tools like Caffeine AI mentioned as a multiplier.  

### On-chain vs. Out-calls Tradeoff:
- Full on-chain AI infeasible without breakthroughs.  
- Near-term: out-calls to external providers still required, but TEEs & IC locality can reduce risks.  
- Developer experience: out-calls add setup burden (accounts, API keys), whereas IC-native AI compute could eliminate friction.  

---

# 🖥️ AI Worker Prototype
- The original AI worker server (4× A100 GPUs) running under ICP was discussed.  
- Demonstrates that AI can be wrapped as a canister API instead of a low-level integration.  

---

# 🔌 Towards Integrated AI Compute in ICP
- Current challenge: how to embed AI compute more deeply into IC while keeping security & decentralization guarantees.  
- Suggestion: leverage existing VM infrastructure (already used for boundary nodes) to host confidential compute VMs with attached GPUs.  
- Key point: inputs go through consensus before reaching the VM → strong assurance on what enters the AI compute environment.  
- Outputs, however, do not go through consensus (same as in replica execution). Trust relies on verified inputs + controlled VM stack.  

---

# 🛡 Confidential Compute Path
Proposal: run side VMs (peripheral compute) with:
- SEV-SNP / TDX hardware-backed attestation.  
- Dedicated software stacks for GPU workloads.  
- Images deployed via IC consensus mechanism (like canister code, but for VM images).  

These “peripheral VMs” would:  
- Be tightly sandboxed (no external network).  
- Connect to replica VMs through VSOC (VM socket), a direct point-to-point channel (no TCP/IP stack).  
- Handle prompts/responses as streams → equivalent to hijacking the current HTTP out-call mechanism, but redirecting to internal secure VMs.  

---

# 🏗️ Implementation Concept
- Treat subnets as distributed virtual machines (DVMS).  
- Attach peripheral VMs with GPUs to these DVMS.  
- Use VSOC tunnels as the internal bus between replica VM ↔ AI VM.  
- Deploy certified Linux VM images via IC consensus (just like canister WASM binaries).  
- Ensure all inputs to AI VM come from consensus-validated subnet messages.  
- Expose results back through canister APIs, so developers interact as with any other canister.  

---

# ❓ Open Questions
- **Value Proposition:** Is the added security & integration meaningful enough for developers/clients compared to simply calling OpenAI/Anthropic APIs?  
- **Governance:** Would the community support the additional ICP rewards needed to run GPU-backed nodes?  
- **Roadmap:** Should this be pursued as a core IC feature, or left to specialized service subnets?  