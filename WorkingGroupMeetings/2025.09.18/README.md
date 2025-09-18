# 2025.09.18 Meeting Summary - DeAI Working Group for the Internet Computer (ICP)

## Short Version
The call explored FPGA-based AI accelerators (e.g., Intel Agilex/Positron) as a flexible, “computer-on-a-card” middle path between expensive NVIDIA GPUs and risky ASICs for ICP. These cards (ARM cores + DDR4/HBM2, PCIe/400 GbE, BMC) run Linux and a transformer-optimized fabric that can load Hugging Face models, with vendors claiming ~2–3× better latency/throughput and energy efficiency vs H100 for mid-size LLMs thanks to mat-vec/dataflow specialization—and they’re field-reprogrammable for ongoing gains. The group discussed ICP fit: standardized 6-year hardware bets, TEE-enabled replica VMs with a simple, low-maintenance sidecar inference stack, and keeping security/determinism by avoiding external network exposure. Next steps center on a roadmap to first prototypes, evaluating vendor ecosystems, and seeding a hardware-oriented developer track (e.g., via ETH Zurich, lower-cost Agilex variants).

### Links shared during the call:
* FPGA: https://en.wikipedia.org/wiki/Field-programmable_gate_array
* Groq engineers interview on their chip design: https://www.youtube.com/watch?v=13pnH_8cBUM
* AI programmed onto FPGA devices: https://youtu.be/JJ-R-Cgo600?si=2QwljkUO7XgTv8kt
* https://youtu.be/lLjnDXYsBUM?si=Byyc2lLwdPONxF13
* https://www.youtube.com/live/hoIMDKrT6jM?si=kF4anKhIbb3mnabI
* https://youtu.be/oeKRtNkx_Ek?si=QSHRZV4Pa5rHvYtU
* https://youtu.be/9bCICtQd9yY?si=RU9jJjrjad4Sm8Y6
* https://youtu.be/PWJNjYspg4A?si=I7sisnNG3SVEW-FH
* Next week's session: Defeating non-determinism in LLM inference
https://github.com/thinking-machines-lab/batch_invariant_ops?utm_source=www.theneurondaily.com&utm_medium=newsletter&utm_campaign=did-ex-openai-cto-mira-s-12b-startup-just-solve-ai-s-biggest-bug&_bhlid=52e4fc9a581173c7bc72f0ca471e98dff387e695
* Free book on Active Inference: https://direct.mit.edu/books/oa-monograph/5299/Active-InferenceThe-Free-Energy-Principle-in-Mind

## Long Version
# Overview
The session focused on FPGA-based accelerators (e.g., Positron / Intel Agilex-class cards) as an alternative to GPUs and ASICs for on-chain AI in the Internet Computer. Discussion covered how FPGAs work at the silicon level, trade-offs against GPUs and ASICs, integration into ICP’s replica model, and potential paths for developer and research involvement.

# Key Takeaways

## 1. FPGA Hardware & Architecture
- **FPGA = Field Programmable Gate Array**:  
  A 2D grid of programmable logic blocks that can be configured to behave like AND/NAND/NOR/etc. gates, then combined into circuits.  
- Acts like a “software-defined chip”: reprogrammable after manufacture, similar to firmware but at the logic-gate level.  
- Cards integrate:  
  - ARM Cortex cores (runs Linux, pre/post-processing)  
  - DDR4 & HBM2 (up to 32 GB)  
  - PCIe Gen4/5 + QSFP 400 GbE I/O  
  - BMC + UART/GPIO management  
- Once programmed, gates persist across power cycles, like flash memory cells.

## 2. Inference Stack & Performance
- Vendors ship a transformer-optimized inference engine implemented in FPGA fabric.  
- Hugging Face transformer binaries can be loaded → converted to FPGA execution graphs.  
- Claims: **2–3× throughput and energy efficiency vs. NVIDIA H100** for mid-size models (e.g., LLaMA-38B).  
- Gains stem from **mat-vec specialization** and **dataflow-centric design** (avoiding GPU bottlenecks).  
- Field reprogrammability = upgrade potential every 6–12 months via firmware.

## 3. Trade-offs: FPGA vs. ASIC vs. GPU
- **ASICs (e.g., Tenstorrent, Croc, TPU-like)**  
  - Hardwired efficiency, but risky if optimized for the wrong paradigm (CNN vs. Transformer → historical failures).  
  - Long design & fab cycles; inflexible to paradigm shifts.  
- **GPUs (NVIDIA A100/H100/Blackwell)**  
  - General-purpose, widely supported, but expensive and power-hungry.  
- **FPGAs**  
  - Reprogrammable, flexible, mid-point between cost and efficiency.  
  - Roughly “one process node behind”: a 7 nm FPGA performs like a 12–14 nm dedicated ASIC.  
  - Still competitive (Ampere GPUs = 12 nm and widely used).  

## 4. ICP Integration & Roadmap
- ICP needs **standardized, long-lifecycle hardware choices** (≈ 6-year bets).  
- Possibility:  
  - Run **TEE-enabled replica VMs** on ARM cores.  
  - Use FPGA fabric for accelerated inference in **peripheral VMs** (attached to replicas, no network exposure).  
  - Preserves ICP’s **security and determinism guarantees**.  
- Critical requirement: keep the **software stack simple** (low-maintenance inference layer, reproducible builds).  
- **Too complex stacks** = burden on node providers and DFINITY’s ops.  

## 5. Developer & Research Angle
- Lower-cost Agilex variants (e.g., Agilex 5, no HBM) = entry point for **developer testing**.  
- Potential to build a **hardware-oriented developer culture** in ICP (ETH Zurich partnership, FPGA training programs).  
- Idea: foster **experimentation with FPGA programming** for AI + replica VM co-design.  

# Open Questions
- How robust are FPGA gains across diverse workloads (beyond mat-vec bottlenecks)?  
- What’s the TEE story on ARM cores, and how does ICP’s security model map to FPGA sidecars?  
- Which subnets should get accelerators, and how to enforce hardware homogeneity?  
- How sustainable are vendor firmware/roadmaps (risk of vendor sunset)?  
- What’s the right roadmap from today’s “no AI hardware” → first FPGA prototypes → production integration?  

# Next Steps
- Explore a **roadmap session**: how to evolve ICP from zero AI hardware toward prototype deployments.  
- Coordinate with **ETH Zurich** (existing DFINITY relationship) on FPGA-based AI research.  
- Evaluate vendor ecosystems (Positron, Agilex, Croc, Tenstorrent, etc.) for long-term fit.  
- Prioritize **simplicity in inference stack design** to match ICP’s reproducible builds model.  