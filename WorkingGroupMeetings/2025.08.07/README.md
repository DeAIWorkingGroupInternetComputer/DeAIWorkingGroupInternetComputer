# 2025.08.07 Meeting Summary - DeAI Working Group for the Internet Computer (ICP)

## Short Version
The ICP Agent Kit, presented by Mert in the DeAI Working Group, is a TypeScript library designed to simplify interaction with Internet Computer (IC) canisters using either direct API calls or natural language prompts processed via OpenAI. It features a modular plugin system (canister, token, identity, cycles) and supports rapid agent development, ideal for educational and developer onboarding use cases. While not an MCP or A2A-ready tool yet, it lays the groundwork for such integrations. Security-wise, prompt clarity and validation are key, especially before mainnet use. Looking ahead, the project aims to evolve into a Language Model-Canister Protocol (LMCP) to enable AI-assisted development in environments like Cursor. Broader discussion emphasized the trend toward small language models for edge use, WebAssembly deployment, and IC's strategic potential to differentiate through tooling and agent-centric infrastructure.

### Links shared during the call:
* ICP Agent Kit on the forum: https://forum.dfinity.org/t/icp-agent-kit-natural-language-interface-for-internet-computer-langchain-based/53712
* ICP Agent KitGitHub: https://github.com/justmert/icp-agent-kit
* ICP Agent KitDocumentation: https://icp-agent.com/plugins/canister#creating-canisters
* WebAssembly: https://www.youtube.com/watch?v=HPA8qmsHQfc
* Data centers: https://www.youtube.com/watch?v=cl1ctf1_JxE
* Small Language Models: https://arxiv.org/pdf/2506.02153
* DeAI Working Group call summaries: https://github.com/DeAIWorkingGroupInternetComputer/DeAIWorkingGroupInternetComputer/tree/main/WorkingGroupMeetings

## Long Version
## 🔧 Main Presentation: ICP Agent Kit

**Presented by:** Mert  
A deep dive into a newly developed TypeScript-based ICP Agent Kit – a developer library designed to simplify interaction with Internet Computer (IC) canisters via natural language prompts or direct API calls.

### ✨ Key Features
- **Plugin architecture**: Four main plugins – `canister`, `token`, `identity`, and `cycles`.
- **Natural Language Interface**: `agent.processNaturalLanguage(prompt)` allows devs to interact with ICP via AI (OpenAI backend) without knowing SDK internals.
- **Direct API Calls**: Optional for users who prefer to specify method calls manually.
- **Demos shown**:
  - Querying a greeting canister with a natural language prompt.
  - Asking “What is my principal ID?” or “What is my account identifier?” and getting responses via AI.
  - Health checks and deployment of agent connector canisters.
  - Personal storage and governance cross-chain demos.

### 🤖 Usage Context
- Not an MCP (Model-Canister Protocol), but could be used to build one.
- Does not currently support agent-to-agent (A2A) communication (ACP), but could add it if demand arises.
- Not compatible with tools like Cursor or CloudyCode directly; it's a standalone library.
- **Use case**: great for educational bootcamps, developer onboarding, and quickly building agent-integrated apps.

### 🔐 Security Considerations
- Since AI executes calls, **prompt clarity is critical**.
- Potential for **hallucinated or incorrect code** if the model interprets prompts loosely.
- A **validation step is advised** before mainnet execution.

### 🛠️ Next Steps
- Planned development of **LMCP (Language Model-Canister Protocol)**, a dev-focused protocol to integrate AI-assisted coding environments (like Cursor) directly with IC development.
- **Vision**: Create an AI development assistant that translates natural language into canister operations (e.g., “create a canister”) and executes via the library in the background.

---

## 🧩 Broader Discussion: Trends in Model Deployment & Strategy

- Growing **emphasis on small language models (SLMs)** for edge deployment and agentic applications, especially supported by NVIDIA’s recent positioning.
- Industry shift: **AGI-capable models → distilled → fine-tuned agents**.
- NVIDIA, OpenAI, and others releasing **dual model formats**: high-end for datacenters, quantized/edge-sized for local use (MacBooks, mobile, browser via WASM).
- **WebAssembly** mentioned as a promising tool to run AI models securely in browsers or lightweight devices.

---

## 🧠 Strategic Takeaways for IC Ecosystem

- IC’s edge in **tooling** (e.g., Caffeine AI, ICP Agent Kit) may be a stronger differentiator than simply hosting models.
- Supporting **agent tools, SDKs, and dev workflows** for deploying agents across edge and canister environments could be key.
- **Ecosystem vision**: blend centralized (datacenter) and decentralized (canister/edge) inference + interaction layers into a unified AI agent infrastructure.