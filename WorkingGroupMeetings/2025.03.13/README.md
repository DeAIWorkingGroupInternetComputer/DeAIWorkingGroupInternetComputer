# 2025.03.13 Meeting Summary - DeAI Working Group for the Internet Computer (ICP)

## Short Version
In today's DeAI Working Group call for the Internet Computer, ETH students introduced an inference engine project using a 1B-parameter Llama 3 model, exploring optimizations via the Mistral RS library and considering alternatives like Candle and Llama.cpp. The group focused on discussions on upgrading hardware to Gen-3 AMD EPYC Zen 5 CPUs and integrating GPUs, highlighting NVIDIA's H100/H200, AMD Instinct, and emerging accelerators such as Tenstorrent to meet ICP’s future AI workload requirements.

### Links shared during the call:
* https://github.com/EricLBuehler/mistral.rs
* original llama.cpp: https://github.com/ggml-org/llama.cpp
* llama.cpp running in a canister of the IC: https://github.com/onicai/llama_cpp_canister
* summary of the max tokens per update call investigation: https://github.com/onicai/llama_cpp_canister?tab=readme-ov-file#appendix-a-max_tokens
* summary of the last hardware-focused call as a reference: https://github.com/DeAIWorkingGroupInternetComputer/DeAIWorkingGroupInternetComputer/tree/main/WorkingGroupMeetings/2025.02.13
* https://resources.nvidia.com/l/en-us-gpu?ncid=no-ncid
* example server: https://www.mitaccomputing.com/en/overview/Barebones/TN85B8261_B8261T85E8HR-2T-N#ov
* https://www.gigabyte.com/Enterprise/Rack-Server/XV23-ZX0-AAJ1-rev-3x#Overview
* https://www.nvidia.com/en-us/data-center/h100/?ncid=no-ncid
* https://www.amd.com/en/products/accelerators/instinct/mi300/mi300x.html
* https://tenstorrent.com/hardware/wormhole
* https://www.modular.com/
* https://blog.vllm.ai/2023/06/20/vllm.html
* https://forum.dfinity.org/t/decreasing-http-outcall-latency-and-cost/28181/7?u=lastmjs

## Long Version
In today's DeAI Working Group call for the Internet Computer, the group welcomed Alice, Daniel, and Arthur, ETH students who will be working on an inference engine for the Internet Computer. Their project initially uses the Llama 3 model (1 billion parameters) provided by Islam. The students introduced their exploration into optimizing inference, particularly discussing the Mistral RS library, which offers SIMD optimizations for CPU inference. The community suggested also considering other libraries like Candle and Llama.cpp for comparison.

The conversation then shifted to discussing potential hardware upgrades for the Internet Computer nodes, emphasizing the Gen-3 AMD EPYC Zen 5 (Turing) architecture and the inclusion of GPU accelerators. These upgrades would significantly improve the computational capabilities, particularly beneficial for running on-chain AI models. Key considerations include power consumption, cooling options (air vs. liquid cooling), costs (estimated at $25,000–30,000 per server without GPUs), and lead times, which could range from one to three months. Participants agreed that further research into pricing, hardware availability, and cooling solutions across multiple regions would be beneficial.

Finally, potential GPU options were discussed, particularly NVIDIA's H100/H200 series and AMD’s Instinct series, alongside other emerging accelerator alternatives like Tenstorrent's solutions. This hardware exploration was highlighted as essential to match future software needs for AI workloads on ICP.