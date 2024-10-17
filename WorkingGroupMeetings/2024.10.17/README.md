# 2024.10.17 Meeting Summary - DeAI Working Group for the Internet Computer (ICP)

## Short Version
In today's DeAI Working Group call for the Internet Computer, the focus was on GPU support for AI applications, exploring two approaches: a specific AI inference API and a more generic GPU exposure. The group discussed the challenges of GPU determinism, the potential flexibility of enabling various use cases, and security considerations. Preliminary testing on NVIDIA A100 cards showed promise for determinism, but further research is needed. The group leans toward the more flexible, generic approach despite its complexity, with a potential launch timeline in 2025 depending on technical readiness and hardware procurement.

### Links shared during the call:
* https://x.com/PrimeIntellect/status/1844814838499037629
* https://www.primeintellect.ai/blog/intellect-1 
* https://github.com/gip/yllama.oc

## Long Version
The DeAI Working Group call for the Internet Computer on October 17, 2024, focused on exploring two potential approaches for GPU integration to enhance AI capabilities. Key topics included GPU determinism, research on inference workloads, and the technical roadmap for GPU support. 

### GPU Determinism Research:
The research indicated that GPUs could behave deterministically under specific conditions, particularly with matrix multiplication and language model inference tasks. Multiple tests showed consistent, identical results, although further testing is required to conclude non-determinism's impact definitively.

### Approach 1: Use-Case-Specific AI Inference API:
This approach focuses on creating a specialized system API for running AI inference. Developers would upload AI models (e.g., ONNX) to the canister, provide an input tensor, and the internet computer would run the inference using GPUs or CPUs depending on the subnet.
- **Advantages**: Simpler to implement, deterministic, supports both GPU and CPU subnets.
- **Disadvantages**: Limited to AI inference, requiring constant maintenance for different AI model formats like ONNX.

### Approach 2: Generic GPU Support:
A more flexible but complex solution, exposing GPUs to developers for any workload (not limited to AI). Developers could write shaders and execute any GPU-based workflow, providing more freedom for custom GPU applications.
- **Advantages**: More flexibility for different use cases, broader application support beyond AI.
- **Disadvantages**: Harder to implement, no guarantee of determinism, possible increased complexity in maintaining.

### Timeline Considerations:
The group discussed the technical feasibility and potential timeline for launching these GPU capabilities, targeting 2025. Concerns about hardware procurement timelines (e.g., for A100 GPUs) were raised, with suggestions to test more widely available hardware like RTX 4090 or A6000 cards.

### Security Considerations:
There were concerns about exposing GPUs to potential exploitation by malicious users, particularly if long-running non-AI workloads could affect the system. One possible mitigation would be timeout mechanisms for GPU-heavy workloads.

The group showed a general preference for Approach 2 due to its flexibility and potential long-term benefits, though it acknowledged the complexity and time investment required.