# 2025.02.20 Meeting Summary - DeAI Working Group for the Internet Computer (ICP)

## Short Version
The ICP LLM Canister was introduced as a new LLM service on the Internet Computer, currently supporting Llama 3.1 (8B parameters) with Rust and Motoko libraries. While the AI worker is centralized for now, decentralization is a key future goal. The system is stateless, using IC’s random beacon for variability in responses, and scalability improvements are being explored. Future plans include expanding language support, integrating Anthropic's MCP for tool calling, and enhancing security and privacy. At ETH Denver, ICP teams will showcase live AI demos, engage in hackathons, and explore cross-chain AI collaborations.

### Links shared during the call:
* New ICP LLM Canister: https://forum.dfinity.org/t/introducing-the-llm-canister-deploy-ai-agents-with-a-few-lines-of-code/41424
* MCP standard: https://modelcontextprotocol.io/introduction
* vLLM is the current industry standard for serving batch requests:  https://docs.vllm.ai/en/latest/
* ETH Denver ICP Events: https://lu.ma/icpevents
* Agents Day at ETH Denver: https://lu.ma/agentsday?locale=en-GB
* Another Agents event: https://lu.ma/e/evt-mHu1Cnw5q8DZjlX?pk=g-5lniIg7Wd13JAFH
* ICP Telegram group for ETH Denver: https://t.me/+TpX7IvvJuqw1MWM0
* ICP Projects at ETH Denver: https://docs.google.com/spreadsheets/d/1GQo-bnIhBuxQMmxPtSobwG3BIUSNtHWbV4zwdnoAt-0/edit?gid=225912498#gid=225912498
* Outlier Ventures event at ETH Denver on the Post Web: https://lu.ma/e/evt-OtkJ3oYnga3ymtg?pk=g-1Ckf3Tmq4i0dCS5
* Environment for creating Fetch.AI agents: https://github.com/JupiterM/Fetch-Ai-Vagrant/tree/main


## Long Version
# Key Announcements & Updates on ICP LLM Canister

## LLM Canister on the IC
A new LLM canister has been released on the Internet Computer (IC), along with Rust and Motoko libraries. This allows developers to interact with and build AI agents in just a few lines of code.

### Model Used
The MVP currently supports Llama 3.1 with 8 billion parameters, but more models and API improvements are planned.

### API Structure
The canister exposes a single API for chat, while additional prompt-handling functionality is provided through the libraries.

### Centralized Setup (For Now)
The AI worker is currently centralized, but there are plans to make it decentralized in the future. There are ongoing discussions on different approaches for decentralization.

---

## Technical Discussion

### Scalability & Performance
Right now, the system operates with a single canister, meaning high usage could lead to bottlenecks. Multiple canisters or payment-based access models may be introduced later.

### Stateless AI Model
The LLM does not store chat history internally—each request must include its context.

### Randomness in Responses
The model uses IC's random beacon as a seed, meaning responses may vary slightly even for the same input. However, there are options to introduce determinism.

---

## Future Considerations

### Expanding Programming Language Support
The team is open to porting the existing Rust and Motoko libraries to Python or TypeScript if there is interest.

### Tool Calling via Model Context Protocol (MCP)
There was a discussion on integrating Anthropic's MCP, which enables LLMs to call external tools. This could allow IC canisters to act as deterministic AI tools.

### Security & Privacy
A key challenge is ensuring that decentralized AI workers process requests securely and privately.

### Inference Engine
Currently, the system uses Ollama for inference. The suggestion was made to explore vLLM, which supports batch requests, potentially improving efficiency.

---

## ETH Denver Conference Preparation

### ICP Presence
Many ICP teams will attend, including DFINITY. There will be bounties, hackathons, and side events.

### Networking & Outreach
Efforts will be made to onboard external teams into the DeAI working group, explore collaborations, and possibly host joint events with other ecosystems.

### Demo Readiness
The team is working on a live AI demo for the booth and exploring physical materials (flyers, QR codes, stickers, etc.) to maximize engagement.

---

## Next Steps & Upcoming Discussions

### Next Call
A session on MCP and its relevance for AI on ICP.

### Scalability Improvements
Continued discussion on decentralized AI worker models.

### Engaging External Teams
Exploring cross-chain AI integrations and demos.
