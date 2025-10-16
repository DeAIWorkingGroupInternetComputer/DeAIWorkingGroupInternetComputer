# 2025.10.16 Meeting Summary - DeAI Working Group for the Internet Computer (ICP)

## Short Version
In today’s call, the group explored why modern FPGAs are emerging as serious, inference-optimized accelerators for transformer LLMs—and how their properties map to IC/DeAI goals. Modern FPGAs have evolved into full SoC-class accelerators that combine reconfigurable logic, on-chip memory, ARM cores, and high-speed networking—making them powerful, deterministic, and upgradable inference engines for transformer models. Case studies like Positron AI’s Llama-3-8B inference show ~4× better performance-per-dollar and ~4.5× higher energy efficiency than NVIDIA H100 GPUs, enabled by dataflow-style architectures and 32 GB on-fabric HBM that minimize memory transfers. Their ability to run fixed-timing, verifiable pipelines and receive remote bitstream upgrades positions FPGAs as a strong complement to GPUs for decentralized, deterministic AI execution on the Internet Computer.

### Links shared during the call:
* https://www.bittware.com/products/positron-atlas/
* https://www.intel.com/content/www/us/en/content-details/775363/fpgas-for-dummies-2nd-intel-special-edition.html
* https://www.amd.com/en/products/adaptive-socs-and-fpgas/versal/hbm-series.htm
* https://www.skyblue.de/en/fpga-main-board-accelerators/intel-agilex/bittware-ia-860m-intel-agilex-7-agm039

## Long Version

Context: Building on last month’s discussion sparked by Positron AI, the group explored why modern FPGAs are emerging as serious, inference-optimized accelerators for transformer LLMs—and how their properties map to IC/DeAI goals.

## FPGA primer (why they’re different)

**What they are:** Reconfigurable 2D fabrics of logic gates with programmable interconnects. Designs are written in Verilog/VHDL, synthesized to a bitstream, and flashed to the board.  
**Trade-off:** ~5–10× more transistors/area than fixed silicon for the same circuit, but you gain upgradability, rapid iteration, and dataflow-centric execution.  
**Design/testing:** FPGAs remain the standard for silicon prototyping before ASIC tape-out.

---

## Modern FPGAs ≠ 1990s FPGAs

Today’s boards are effectively computers on a card (SoC-like) with “hard IP” blocks: ARM cores, PCIe/Ethernet PHYs, transceivers, BMC for out-of-band management, etc.  
The fabric includes distributed SRAM/BRAM and DSP slices (matrix/vector engines akin to tensor cores), enabling pipelined, deterministic dataflow.  
**Vendors noted:** Xilinx/AMD, Altera/Intel (spun out), Lattice, plus board makers like Molex Bitware.

---

## Productization & IP models

You can license pre-compiled transformer inference IP (bitstreams) and flash it onto a compatible card, or buy pre-loaded, tested accelerators/servers.  
**Lifecycle updates:** Linux exposes standard interfaces for remote bitstream upgrades over PCIe/USB; reconfiguration is as routine as software deploys (microcode analogy).

---

## Case study: Positron AI (inference on FPGA)

**Workload:** Llama-3 8B.  
**Economics:** Card around US$18k; claimed ~4× perf/$ vs NVIDIA H100 (~US$20k) and ~4.5× better power efficiency.  
**Scale-out:** An 8-card “Atlas” inference server reportedly beats a DGX H200 in inference-specific throughput/efficiency.  
**Why it works:** FPGA dataflow keeps weights/activations on-fabric (SRAM + 32 GB HBM per card), minimizing off-chip traffic; perfect fit for forward-only inference. GPUs are superb for training, but under-utilized for token-by-token inference.

---

## Hardware specifics (Bitware board used by Positron)

- **I/O:** 3 × 400 GbE (≈ 1.2 Tb/s) — far beyond PCIe Gen5 ×16 (~128 Gb/s); can directly mesh cards over 400 GbE.  
- **Compute/ctrl:** ARM HPS (4 cores + DDR4) running Linux; BMC for remote mgmt.  
- **Storage:** M.2 NVMe (PCIe Gen4) and external MCIO options.  
- **Memory:** 32 GB HBM on-chip for fast model/activation flow.

---

## Model coverage & limits

Bitstreams target the transformer architecture generically (not a single model), so multiple LLMs can run if they’re transformer-based.  
These designs are inference-only; training isn’t feasible/practical on these devices.

---

## Why this matters for the Internet Computer (IC/DeAI)

**Determinism:** Strictly timed, systolic, clock-domain pipelines make latency/throughput highly predictable, aligning with replicated, verifiable compute needs.  
**Upgradability:** Remote bitstream updates fit decentralized ops and long-lived nodes.  
**Networking:** Built-in 400 GbE enables efficient multi-card model sharding without relying solely on PCIe, useful for scale-out inference services.

---

## Key takeaways

- FPGAs have matured into full SoC accelerators with on-fabric memory and DSPs, ideal for transformer inference.  
- Positron-style results suggest compelling perf/$ and power efficiency vs data-center GPUs for 8–13B-class models.  
- Deterministic timing + upgradable bitstreams make FPGAs particularly attractive for IC/DeAI where verifiability, predictability, and remote ops matter.  
- The path forward: evaluate FPGA-based inference nodes (single and clustered over 400 GbE) as a complementary track to GPU deployments on the IC.