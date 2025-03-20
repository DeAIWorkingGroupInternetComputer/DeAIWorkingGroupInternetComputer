# 2025.03.20 Meeting Summary - DeAI Working Group for the Internet Computer (ICP)

## Short Version
Today's DeAI Working Group call for the Internet Computer discussed recent advancements in efficiently running Large Language Models (LLMs) on-chain. The DeAI Chat team introduced a novel "chunking" strategy that sequentially processes small vector chunks, significantly reducing memory usage and enabling models with up to 1.5 billion parameters to run effectively. They demonstrated both an off-chain client method, optimizing speed through query calls, and an on-chain client method emphasizing decentralization via update calls, albeit with slower responses. Additionally, strategic paths for decentralizing AI worker nodes were explored: the "Classic" model, which aligns with current security but faces cost and scalability limitations, and the "Badlands" approach, which supports open participation and scalability but requires addressing security and decentralization concerns.

### Links shared during the call:
* https://x.com/deai_chat?s=21 
* https://drive.google.com/drive/folders/1RIQkolzGYXawY6F7C1wU9Gihp46AA7ZP
* https://vgjrt-uyaaa-aaaal-qsiaq-cai.icp0.io/
* https://forum.dfinity.org/t/introducing-the-llm-canister-deploy-ai-agents-with-a-few-lines-of-code/41424/32

## Long Version
Today's DeAI Working Group call for the Internet Computer focused on discussing recent advancements and strategic approaches to running Large Language Models (LLMs) efficiently on-chain.

The DeAI Chat team shared their latest work on optimizing LLM execution through a novel "chunking" strategy. Instead of loading entire models into memory, their approach involves sequentially running small vector chunks, significantly reducing heap memory usage and enabling models with around 1 to 1.5 billion parameters to run efficiently. The team demonstrated two methods:

- **Off-chain client method:** Utilizing query calls for rapid, repeated requests, leading to efficient processing and quicker response times.
- **On-chain client method:** Employing update calls to maintain decentralization but facing slower response times due to consensus requirements. Despite this, it successfully demonstrated the feasibility of larger model execution on-chain.

The team is working to further refine their methods, such as caching initial computations and potentially expanding to support larger models and longer responses in the future.

In the second part of the call, Islam discussed two strategic paths for decentralizing the AI worker nodes responsible for serving foundational LLM models:

- **Classic Approach:**
  - Node providers would acquire specified hardware and be compensated in ICP, maintaining consistency with current IC security models.
  - Drawbacks include high costs, limited scalability, and risk of hardware obsolescence due to rapid technological evolution.

- **"Badlands" Approach:**
  - A more open, permissionless protocol allowing anyone to host LLMs with incentives for reliability and efficiency.
  - Benefits include future-proofing, lower cost, scalability, and increased community participation. However, it raises concerns about decentralization integrity and the security of prompt-response handling.

The call participants discussed the importance of security, privacy, and the consistency of software stacks across decentralized nodes, highlighting these as critical considerations for moving forward.