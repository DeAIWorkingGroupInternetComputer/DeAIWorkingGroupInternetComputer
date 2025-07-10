# 2025.07.10 Meeting Summary - DeAI Working Group for the Internet Computer (ICP)

## Short Version
In today’s call, we had a demo by the BIPQuantum team. BIPQuantum is an ICP-based platform that streamlines intellectual property (IP) registration and protection by minting IP as blockchain-based NFTs and issuing certificates, with future plans for AI-driven automation, royalties, and integration into US corporate certification workflows. Built on a multi-canister architecture, it currently supports small on-chain LLMs for IP-related queries, while exploring off-chain and hybrid approaches to overcome ICP’s memory and instruction constraints. With a user base of scientists, AI creators, and entrepreneurs, the project also aims to fractionalize IP for funding innovation. Early adoption of blockchain IP recognition in jurisdictions like France and China supports its vision, as the team actively develops voice and AI integrations to enhance decentralized, quantum-resistant IP management.

### Links shared during the call:
* https://linktr.ee/bipquantum
* https://dapp.bipquantum.com/login
* https://github.com/Recursive-Emergence/RE
* https://speckled-icebreaker-5e8.notion.site/bIPQuantum-White-paper-0c2a9a2d6d844e68b7646b2778cb12ee
* https://github.com/onicai/llama_cpp_canister?tab=readme-ov-file#appendix-a-max_tokens
* https://forum.dfinity.org/t/introducing-the-llm-canister-deploy-ai-agents-with-a-few-lines-of-code/41424/62
* https://github.com/DeAIWorkingGroupInternetComputer/DeAIWorkingGroupInternetComputer/tree/main/Projects
* https://github.com/patnorris/DecentralizedAIonIC
* https://devinci.onicai.com/
* https://icgpt.onicai.com/

## Long Version
# Project Overview: BIPQuantum

BIPQuantum is an ICP-based solution focused on simplifying intellectual property (IP) registration and protection using blockchain technology. It's aiming for quantum-resistant IP solutions.  
Supported by Quantum Leap Lab and Accelerator.

## Features and Goals
- Offers automated IP registration, minting IP as ICRC NFTs.
- Generates IP certificates and integrates them into marketplace listings.
- Plans for AI-assisted automation and royalties through smart contracts.
- Bridges blockchain-based NFT certificates with US corporate certification processes, creating digital twins of IP assets.

## Technical Architecture
- Consists of 5 canisters plus Internet Identity integration:
  - Frontend and backend (Motoko-based) handle core logic for minting IP NFTs.
  - NFT Ledger manages NFT IP assets.
  - ICRC-3 Ledger handles fungible token transactions.
  - Proxy Canister for IPv4 HTTPS calls (e.g., OpenAI integrations).

## Challenges and Development Insights
- Current limitations around storage space for full LLM deployment.
- Using HTTPS calls for OpenAI GPT interactions.
- Initial image and metadata storage in the ledger canister present challenges; future plans include moving metadata off-ledger.
- Need to implement an audit trail for easy transaction look-up (potentially using an index canister like an "Etherscan" equivalent).
- Currently exploring stable memory storage strategies and canister performance optimizations.

## AI Integration and Model Deployment
- Successfully tested deployment of smaller AI models (TinyLlama, Llama 3, 1B–7B parameters) directly on ICP.
- Identified ICP limitations:
  - Canister memory limit: ~4GB per canister.
  - Instructions limit: 5 billion per call.
  - Response size limit: 3MB.
  - Concurrency is currently limited (approximately two concurrent sessions per canister), requires optimization.
- Considering XTTS (open-source text-to-speech) and Whisper for speech functionalities, assessing ICP compatibility.
- Aiming to deploy small NLP-focused LLMs sufficient for IP-related queries.

## Community Contributions & Recommendations
- Discussed using llama.cpp for optimized LLM deployment on ICP, highlighting experiences with smaller models (e.g., Qwen 2.5 with 630M parameters).
- Shared resources:
  - Examples of vector databases running on ICP.
  - DFINITY’s LLM canister for off-chain large model integrations.

## Whisper.cpp Integration
- Idea to port Whisper.cpp (by the same developer as llama.cpp) to ICP canisters.
- Whisper.cpp has been successfully used locally, but ICP deployment and performance remain untested.
- If Whisper.cpp cannot run efficiently on-chain, browser-based alternatives will be explored to maintain full decentralization.

## Community and Collaboration
- Developers encouraged to share progress, issues, or interesting findings in Discord's decentralized AI channel.
- Participants expressed commitment to maintaining decentralization, avoiding Web2 architecture.

## AI Integration and Interaction Use Cases
- BIPQuantum aims for user-friendly interactions, focusing on queries related to intellectual property (IP), legal frameworks, product identity, and IP registration.
- Future goals include implementing voice interactions through third-party APIs like Level Labs.
- Plans to integrate their content into LLMs through vectorization and fine-tuning for targeted answers.

## Technical Limitations and Strategies
- Direct on-chain hosting is feasible for smaller LLMs (up to 3B parameters), but larger models (around 8B parameters) may require off-chain or hybrid approaches.
- For intensive use cases, off-chain hosting (e.g., RunPod, Hyperstack) may be utilized to manage latency and user experience.

## Demonstration: BIPQuantum Platform
- Presented user interface, illustrating IP creation through blockchain certificates and NFTs.
- Offers AI-assisted or manual IP creation, adaptable based on user expertise (beginner, intermediate, advanced).
- Provides detailed responses and guidance on IP-related questions, integrated with voice capabilities.
- Facilitates easy minting and marketplace listing of IP NFTs, complete with customizable licensing and royalties.

## IP Monetization and User Base
- Current users primarily include AI creators, entrepreneurs, and scientists.
- Aims to empower users by fractionalizing IP for funding research and innovation.
- Initial focus on pre-patent documentation and blockchain IP certificates, with ambitions for full patent verification processes in future phases.

## Jurisdictional Recognition of Blockchain IP
- Growing global acceptance of blockchain data as legitimate IP proof.
- Official recognition in jurisdictions including France, China, UAE, and advancing rapidly in Europe.
- North America slower in adoption but steadily progressing.

## Next Steps and Open Questions
- Evaluate index canisters for improved audit trails and transaction visibility.
- Further investigate performance and concurrency of LLMs on ICP.
- Explore compatibility and integration of Whisper and XTTS models for voice interactions.

---

The session concluded emphasizing the potential and early-stage nature of decentralized AI, highlighting the ongoing exploration, research, and development opportunities within the community.