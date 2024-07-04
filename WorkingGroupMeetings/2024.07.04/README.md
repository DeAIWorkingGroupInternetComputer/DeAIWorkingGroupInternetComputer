# 2024.07.04 Meeting Summary - DeAI Working Group for the Internet Computer (ICP)

## Short Version
In discussing the implementation of larger language models on the Internet Computer (IC), progress was highlighted in creating canisters for tensor computations despite memory constraints. Key discussions included the slow manual reimplementation of models for IC and the suggestion to use tools like PyTorch and TinyGrad for efficiency. Challenges with stable memory due to bugs and inefficiency were addressed, with proposed direct memory management improvements. The benefits of using frameworks like PyTorch and ONNX were emphasized, along with the potential of the Rust library Candle. Horizontal scaling, federated learning, and the IC's decentralized data ownership were explored as future directions. Action items include experimenting with tools like TinyGrad and federated learning, improving stable memory handling, and fostering developer collaboration.

### Links shared during the call:
* https://docs.google.com/forms/d/e/1FAIpQLSeZU-6BkFXoNPB9i1P3g8Wl6hjIA_wrkFOaBpu4yzKgRjMumA/viewform
* https://github.com/gip/yllama.rs
* https://github.com/gip/yllama.oc
* https://www.youtube.com/watch?v=13pnH_8cBUM&list=WL&index=102
* https://woglz-oqaaa-aaaal-act2q-cai.icp0.io/
* https://github.com/jeshli/rust-connect-py-ai-to-ic
* https://github.com/jeshli/tract-ic-ai
* https://github.com/tinygrad/tinygrad
* https://github.com/huggingface/candle
* https://0g.ai/

## Long Version

### Background and Progress

Discussed the implementation of larger language models, particularly inference, on the Internet Computer (IC). Highlighted the challenges related to data and compute aspects and shared progress on creating canisters capable of handling tensor computations despite memory constraints. Demonstrated current limitations with stable memory and the necessity of avoiding it due to instability.

### Key Topics and Discussions

### Model Implementation and Iteration
- The manual process of reimplementing models for IC is too slow for AI research and development.
- Suggested leveraging existing tools like PyTorch to create models in Python, then target GPUs or CPUs.
- Mentioned exploring TinyGrad, a lightweight alternative to PyTorch, for potential integration with IC due to its simplicity.

### Challenges with Stable Memory
- Two main issues: bugs in IC stable memory libraries and inefficiency in data access.
- Proposed managing memory directly to improve performance, though it requires developer trust.

### Frameworks and Tooling
- Discussed the benefits of using tools like PyTorch and ONNX for training and deploying models on IC.
- Highlighted the potential of Candle, a Hugging Face-backed Rust library, despite the need for Rust expertise.
- Emphasized the importance of making it easy for developers to deploy AI models on IC without needing deep knowledge of its intricacies.

### Horizontal Scaling and Compute Bandwidth
- Explored the idea of breaking down models into smaller modules for horizontal scaling across multiple canisters.
- Acknowledged the significant memory bandwidth requirements for AI computations and IC's current limitations.

### Federated Learning and Data Ownership
- Proposed federated learning as a short-term solution, with IC coordinating training and aggregating weights from client-side computations.
- Long-term solutions would involve integrating GPU infrastructure.
- Emphasized the IC's potential for decentralized data ownership, allowing collaborative AI development while maintaining data integrity and security.

## Additional Thoughts and Future Directions
- Specialized hardware, like Grok, for high throughput and efficient data processing.
- Recognized the value of owning data over compute resources due to the future commoditization of compute.
- Suggested aligning on a strategic approach to leverage IC's strengths in data decentralization and collaborative ownership.

## Action Items
- Explore and experiment with tools like TinyGrad, Candle, and federated learning approaches.
- Consider creating connectors that make IC a target environment for existing AI tools.
- Continue discussions on improving stable memory handling and horizontal scaling of canisters.
- Foster collaboration among developers working on related initiatives to maximize synergies and innovation.




