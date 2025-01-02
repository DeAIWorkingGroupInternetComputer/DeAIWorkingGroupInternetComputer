# 2024.11.07 Meeting Summary - DeAI Working Group for the Internet Computer (ICP)

## Short Version
The DeAI Working Group for the Internet Computer discussed the challenges and opportunities of integrating advanced hardware capabilities, such as high-performance GPUs and PCIe Gen 5 cards, into the ecosystem. The conversation focused on designing a flexible architecture that supports both WebAssembly (WASM) and more optimized computation models like MLIR, enabling efficient execution of AI workloads. Emphasis was placed on ensuring future-proofing and scalability, balancing cost and performance, and leveraging industry-standard protocols like CXL for high-bandwidth memory and CPU interconnects. The group highlighted the importance of collaboration and planning to facilitate a seamless transition to the next generation of node hardware.

### Links shared during the call:
* https://forum.dfinity.org/t/decentralised-traiding-competitions/36814
* https://en.wikipedia.org/wiki/Compute_Express_Link
* https://computeexpresslink.org/ 
* https://en.wikipedia.org/wiki/InfiniBand
* https://arxiv.org/pdf/2409.03864
* https://arxiv.org/abs/2002.11054
* https://mlir.llvm.org/ 
* DeAI manifesto: https://vexj4-tiaaa-aaaan-qzn7a-cai.icp0.io/

## Long Version
## Overview
The call revolved around discussing the next generation of hardware infrastructure for the Internet Computer, emphasizing how it could support advanced computational needs, including AI model execution. The participants highlighted the importance of striking a balance between performance, flexibility, and cost-effectiveness in hardware selection while maintaining compatibility with evolving technologies and standards.

## Key Points

### Software Stack Considerations
- There was a discussion about the current limitations of the software stack in canisters and the need for an enhanced approach that leverages more of the hardware’s computational power.
- The use of MLIR (Multi-Level Intermediate Representation) was considered for enabling a more flexible computation model, particularly in deploying AI models efficiently.

### Hardware Evolution
- Upgrading to the latest CPU architecture, such as Zen 5 cores, was discussed as a way to improve performance significantly. Newer CPUs provide enhancements like optimized AVX-512 SIMD instructions, which can accelerate computations beyond what current WebAssembly (WASM) implementations offer.
- The potential to support multiple PCIe Gen 5 cards was mentioned as a way to future-proof the infrastructure and provide more options for acceleration, including GPUs and other AI accelerators.

### Emerging Standards
- The conversation touched on the importance of adopting open standards like CXL2 (Compute Express Link) for high-bandwidth memory and device interconnects. This approach would support diverse hardware accelerators and keep the platform flexible.
- Participants highlighted that keeping the system open to future hardware advancements, including neuromorphic chips and quantum computing, is strategic.

### Strategic Approach
- The group leaned towards a staged approach to hardware upgrades. The idea is to first implement hardware that brings immediate performance benefits and then expand capacity gradually by adding accelerators.
- There was consensus on the importance of maintaining flexibility and avoiding locking the ecosystem into specific vendors or proprietary standards.

### Next Steps and Collaboration
- There was a suggestion to schedule a dedicated session to delve deeper into these hardware considerations, inviting relevant working groups like the Scalability and Performance group.
- The importance of collaboration and input from the community was emphasized to ensure the chosen hardware spec is efficient, cost-effective, and aligned with future computational needs.

This call emphasized thoughtful planning and the need to adapt to rapid advancements in hardware and AI technologies while prioritizing cost management and performance scalability.
