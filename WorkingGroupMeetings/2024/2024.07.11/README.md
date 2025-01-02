# 2024.07.11 Meeting Summary - DeAI Working Group for the Internet Computer (ICP)

## Short Version
In today's DeAI Working Group call, Vincent presented his master thesis work, focusing on encryption and machine learning models deployed on the Internet Computer, sharing a prototype link (https://zvrui-xqaaa-aaaao-a3pbq-cai.icp0.io/) and the code repository (https://github.com/vince2git/ic-secure-ml). Key discussions covered encryption key exchanges, secure data handling, and using the linfa rust library for benchmarking machine learning models. Vincent detailed the architecture involving t-SNE for clustering and neural network training on the MNIST dataset. Icarus shared insights from the Node provider ICP lab event in Zurich, discussing hardware options, including AMD CPUs with SIMD extensions and integrated CPU-GPU architectures for AI on the IC blockchain (https://forum.dfinity.org/t/technical-working-group-node-providers/30255/7?u=icarus). Challenges of accessing GPU functionality from the WASM runtime and potential solutions through host functions were explored. Future directions emphasized collaboration between node providers and Dfinity engineers, forming a working group to focus on accelerated hardware integration. Open discussions addressed hardware setups, high-level host functions, ONNX for AI model deployment, and the importance of supporting frameworks like PyTorch. Community involvement was encouraged to share benchmarks, explore parallelism, and contribute to ongoing discussions for collective problem-solving.

### Links shared during the call:
* https://zvrui-xqaaa-aaaao-a3pbq-cai.icp0.io/
* https://github.com/vince2git/ic-secure-ml
* https://forum.dfinity.org/t/technical-working-group-node-providers/30255/7?u=icarus
* https://wasmedge.org/book/en/sdk/rust/table_and_funcref.html?highlight="host%20function"#define-host-function
* https://github.com/modclub-app/rust-connect-py-ai-to-ic/tree/main/python
* Support for DeAI projects: https://docs.google.com/forms/d/e/1FAIpQLSeZU-6BkFXoNPB9i1P3g8Wl6hjIA_wrkFOaBpu4yzKgRjMumA/viewform
* DeAI manifesto: https://docs.google.com/document/d/1GM_QzDhU2DAzWm3C5RzU861qEje2lzy7Un_l_dYdhvc/edit#heading=h.8jg466jkf1fh
* DeAI docs: https://docs.google.com/document/d/1tf6kbzE2Vqxb5I6JUWZzJJpQ0qmGXkOfNqcU4yBWOSQ/edit#heading=h.at20hu62va02
* DeAI repo for PR (to add your project): https://github.com/DeAIWorkingGroupInternetComputer/DeAIWorkingGroupInternetComputer/tree/main/Projects

## Long Version

## Vincent's Presentation on Encryption and Machine Learning Models

## Introduction and Welcome
- Vincent presented his work for his master thesis.
- Shared a link to a prototype deployed on the Internet Computer: [Prototype](https://zvrui-xqaaa-aaaao-a3pbq-cai.icp0.io/) (code: [GitHub Repository](https://github.com/vince2git/ic-secure-ml))

## Key Topics Discussed

### Encryption Key Exchange
- Initial steps involve exchanging public keys between the client and the canister for secure communication.

### Machine Learning Models
- Use of the linfa rust library for machine learning models.
- Benchmarking models on both local browsers and canisters.
- Detailed explanation of parameter adjustments like principal component analysis, perplexity, threshold, and iterations.

### Secure Data Handling
- Data is encrypted before sending to the IC, processed, and then encrypted results are sent back to the client.
- Session management involves unique IDs, secret keys, and public keys for secure transactions.

### Architecture of the Solution
- Described the backend encryption, decryption, and model processing.
- Explained the use of t-SNE for dimensionality reduction and clustering.
- Discussed the client-side setup and how it interacts with the front-end canister.

### Neural Network Training
- Trained a commercial neural net on the MNIST dataset.
- Described the neural net architecture involving convolutional layers and dense layers.
- Mentioned ongoing work and future plans for better implementation.

## Icarus' Insights from ICP Lab for Node Providers and Hardware Options

### Context and Overview
- Discussed an ICP lab event for node providers held at Dfinity headquarters in Zurich.
- Mentioned the significance of discussions around hardware options for AI on the IC blockchain.

### Hardware Options and SIMD Extensions
- Talk focused on existing and potential hardware to support AI workloads on the IC ([Forum Post](https://forum.dfinity.org/t/technical-working-group-node-providers/30255/7?u=icarus))
- Explored options like the latest AMD CPUs with more powerful vector extensions.
- Detailed the possibility of using integrated CPU-GPU architectures for better performance.

### Challenges and Solutions
- Highlighted the complexity of accessing GPU functionality from the WASM runtime.
- Discussed the potential for using host functions as a shortcut to leverage hardware accelerations.
- Mentioned the difficulties of ensuring stability and determinism in such setups.

### Future Directions
- Emphasized the need for collaboration between node providers and Dfinity engineers.
- Proposed forming a working group to focus on accelerated hardware and its integration with the IC.

### Open Discussion and Questions
- Addressed questions about the feasibility of different hardware setups.
- Discussed the limitations and potential of using high-level host functions to access GPU accelerations.

## Additional Discussion Points

### WASM Runtime and Hardware Access
- Acknowledged the current limitations of the WASM runtime in accessing GPU functionalities.
- Explored the idea of using WASM as a gluing layer, with actual computations happening outside WASM through custom implementations.

### Potential Tools and Frameworks
- Considered the use of ONNX for portable AI model deployment.
- Discussed the importance of supporting popular frameworks like PyTorch for broader adoption.

### Technical and Practical Considerations
- Addressed concerns about hardware stability and the frequency of GPU failures.
- Highlighted the need for robust planning to handle hardware-related issues effectively.

## Feedback and Next Steps
- Encouraged sharing of benchmarks and results, especially regarding SIMD improvements.
- Urged continued exploration of parallelism and optimizations to enhance the IC’s capabilities for AI workloads.

## Community Involvement
- Invited participants to contribute to the ongoing discussions and share their insights on GitHub and other platforms.
- Emphasized the collaborative nature of the working group and the importance of collective problem-solving.




