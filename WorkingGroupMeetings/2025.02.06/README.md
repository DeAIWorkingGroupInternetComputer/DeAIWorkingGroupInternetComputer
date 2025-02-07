# 2025.02.06 Meeting Summary - DeAI Working Group for the Internet Computer (ICP)

## Short Version
Yan Qing from IC Panda presented the Anda AI agent framework and its integration with DeepSeek and ICP. Anda, a Rust-based framework, focuses on decentralized AI agents with secure execution using trusted execution environments (TEEs) and encrypted memory on ICP. Community efforts include upcoming developer documentation, a hackathon, and grants. Future directions involve multi-agent coordination, improved infrastructure, and expanding real-world AI agent use cases on ICP.

### Links shared during the call:
* Anda framework presentation: https://github.com/ldclabs/anda/discussions/2
* Chinese version: https://www.youtube.com/watch?v=J-b35nUc0lY
* English version: https://www.youtube.com/watch?v=CXpoo8HQSaE
* Cohere Embeddings: https://cohere.com/
* Next PT/FR ICP HUB bootcamp: https://lu.ma/5o20vabw
* ICP AI projects that use Rust (not fully complete and up to date though): https://github.com/DeAIWorkingGroupInternetComputer/DeAIWorkingGroupInternetComputer/tree/main/Projects

## Long Version

## Key Topics Discussed:

### Developer Grants from the DFINITY Foundation
- Four new developer grants were announced.
- Projects include various AI and decentralized infrastructure solutions.

### Presentation by Yan Qing on the AI Agent Framework "Anda"
- Yan Qing introduced the Anda framework, a Rust-based AI agent framework designed for Web3 applications.
- The framework focuses on modular, decentralized AI agents that can collaborate to solve domain-specific problems.
- Emphasized the difference between AI applications (task-based tools) and AI agents (autonomous, proactive systems).
- A 20-minute pre-recorded video was presented with AI-translated English audio: [Watch on YouTube](https://www.youtube.com/watch?v=CXpoo8HQSaE).

### IC Panda’s Integration with DeepSeek and ICP
- IC Panda AI Agent is built on the Internet Computer (ICP) and recently became the first AI agent framework integrated into the DeepSeek repository.
- IC Panda’s trusted execution environment (TEE) runs on AWS Nitro Enclaves, with plans to add Intel SGX and potentially AMD SEV-SNP support.

### Technical Deep-Dive into Anda
- Web3-native AI agent framework, different from existing Web2-focused solutions like OpenAI.
- Uses Rust and focuses on secure, decentralized execution.
- Implements function calling for LLMs to interact with the external world (e.g., fetching real-time data, performing transactions).
- Supports encrypted, persistent memory stored on the ICP blockchain via the LanceDB database.
- Utilizes CBOR (Concise Binary Object Representation) instead of JSON for efficient data serialization and encryption.

### Trusted Execution Environments (TEEs) & Security
- AWS Nitro chosen for maturity, but plans to support Intel SGX.
- Discussion on latency issues and cold start mitigation.
- TEEs allow AI agents to execute securely without leaking sensitive data.

### Embedding & Retrieval-Augmented Generation (RAG)
- Anda currently uses Cohere embeddings instead of DeepSeek, as DeepSeek doesn’t provide built-in embedding functions.
- RAG to improve AI agent memory and responsiveness.

### DeepSeek & ICP AI Integration
- DeepSeek models support OpenAI-compatible APIs, making integration straightforward.
- **Challenges:** Frequent DDoS attacks on DeepSeek servers impact uptime.
- **DeepSeek's collaboration with Anda:** Some Anda tools were merged into DeepSeek's repository.

### Community Contributions & Next Steps
- Developer documentation and tutorials for Anda are expected within two weeks.
- Upcoming hackathon and developer grants to encourage adoption.
- Collaboration with ICP Hub and DFINITY Foundation to fund and expand AI agent use cases.

### Next Steps & Open Questions
- Further exploration of multi-agent coordination and communication protocols.
- Plans for better infrastructure support for low-latency AI agents.
- Encouraging more real-world use cases for AI agents on ICP.

## Key Takeaways:
- Anda is pioneering a decentralized AI agent ecosystem on ICP.
- Integration with DeepSeek and ICP shows promising potential for AI on Web3.
- Security and efficiency are major priorities, with TEE adoption and encrypted memory storage.
- Community involvement is crucial to scaling Anda, and developer participation is highly encouraged.
- The session concluded with Q&A and discussions on future integrations, optimizations, and grant programs.
