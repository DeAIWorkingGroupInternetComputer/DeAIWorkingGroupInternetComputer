# 2025.10.02 Meeting Summary - DeAI Working Group for the Internet Computer (ICP)

## Short Version
The group aligned on practical limits of running large AI fully inside IC’s WASM/consensus, explored paths to higher throughput via async “sidecar” compute on node hardware (and future accelerators), and proposed a parallel initiative to standardize trust/minimal-trust tooling for agents (identity, reputation, registries). A recurring monthly session for hardware acceleration will continue, and a new monthly track for agent tooling & standards is proposed. Pub/Sub on IC (ICRC-77/-72; “ICAIBus”) was highlighted as a fit for async AI workflows. Next week features ICP Coder (Motoko AI assistant); an FPGA deep-dive update is planned in 2 weeks.

### Links shared during the call:
* https://forum.dfinity.org/t/trustless-agents-on-icp/57859
* https://eips.ethereum.org/EIPS/eip-8004
* https://forum.dfinity.org/t/icaibus-internet-computer-ai-bus-pubsub-made-easy-on-the-ic/40606

## Long Version
## Key discussion points

* Why WASM/consensus is the bottleneck:
  Execution time per canister round + global consensus latency across ~13 nodes caps deterministic on-chain compute for LLMs.

* Ways to push the ceiling inside today’s model:

  * Replica/WASM improvements and scheduling optimizations.
  * Subnet tuning (lower network distance) for modest gains.
  * Newer node hardware; exploiting CPU SIMD (WASM up to 128-bit vs EPYC 512-bit capability).

* Beyond the interpreter: async sidecar compute on node hardware:
  Introduce a protocol-level async call-out from canisters to a VM on each node that can use more CPU cores/RAM and optionally GPU/FPGA/ASIC. Canisters submit jobs; results are polled/callback in later rounds.

* Replication choices: run on all 13 nodes for deterministic confirmation vs. round-robin/single instance for speed.

* Hardware acceleration track:
  Keep a monthly focus on accelerated infrastructure for AI on IC. FPGAs are increasingly compelling (modern fabric includes matrix/vector units).

## Agent tooling & “trustless agents” (complementary track)

* Prefer framing as tooling that makes agents more trustless (identity, reputation, validation registries) rather than fully “trustless agents.”
* Proposal: establish a monthly call focused on standardizing and showcasing these tools (MCP/A2A-adjacent topics), and involve DFINITY where possible.
* Vision: an ICP-wide coordination layer where developers specify parameters (cost, privacy, model class, locality) and the platform routes to on-chain tiny models, node-side accelerators, Web2 APIs, or on-device AI—transparent selection rather than hard-coded endpoints.

## Related ecosystem pointers

* Pub/Sub on IC for async AI: ICRC-77/-72 “ICAIBus” was cited as a good fit for queuing jobs, notifications, monetization, and hub-style routing across independent providers.

## Concrete next steps / actions

* Start a catalog of existing AI tools on ICP (baseline for standardization and plug-and-play demos).
* Continue scoping the async sidecar compute concept with DFINITY for feasibility and interface details.

## Upcoming sessions

* Next week: GianM — “ICP Coder” (AI assistant for Motoko).
* 2 weeks: Icarus — FPGA update session (capabilities, recent releases, and performance observations).