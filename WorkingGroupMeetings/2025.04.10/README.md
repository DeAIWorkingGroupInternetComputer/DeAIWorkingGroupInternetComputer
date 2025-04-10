# 2025.04.10 Meeting Summary - DeAI Working Group for the Internet Computer (ICP)

## Short Version
In this session, the group explored recent developments in open-source AI and emerging agent protocols, in particular the Model Context Protocol (MCP). The highlight was a demo by Long, showcasing the first integration of MCP with the Internet Computer (ICP), enabling AI agents to interact with blockchain tools like the NNS and perform actions such as proposal voting and wallet authentication. Discussions covered technical challenges (e.g., overlapping endpoints, authentication security, lack of full server-sent event support), the potential of self-sovereign AI agents, and next steps including developer tooling and upcoming sessions on AI infrastructure and on-chain agents.

### Links shared during the call:
* @baolongt ICP MCP server template: https://github.com/baolongt/mcp-server-template-ic
* @baolongt SNS MCP server: https://github.com/baolongt/sns-mcp-server
* MCP: https://www.anthropic.com/news/model-context-protocol
* Forum discussion on MCP: https://forum.dfinity.org/t/coordinated-plan-on-supporting-mcp-for-vibe-coding-and-ai-agents/43181
* https://github.com/solana-foundation/solana-dev-mcp
* MCP supported clients: https://modelcontextprotocol.io/clients
* https://mcp.so/
* https://smithery.ai/
* https://mcpservers.org/remote-mcp-servers

## Long Version
## General AI Updates
- Open-source AI models were discussed, including a high-performing object detection model with transparent datasets and training regimens.
- Mention of LLaMA 4 and the excitement around its capabilities.
- Google has introduced its own “Agent-to-Agent” protocol ([link](https://developers.googleblog.com/en/a2a-a-new-era-of-agent-interoperability/)), relevant to the group’s work with MCP (Model Context Protocol).

---

## 🚀 Main Session: Demo by Long
Long presented his work integrating the MCP protocol with the Internet Computer (ICP), marking the first of such implementations.

### Key Highlights:

#### MCP Overview:
- MCP is an open standard to connect AI agents with tools, APIs, and databases.
- It simplifies development and allows agents to access real-time information.

#### Architecture:
- MCP consists of three parts: the AI agent (client), MCP server (host), and external tools.
- The server acts as a bridge between the agent and data sources.

#### ICP Implementation:
- Long demonstrated an AI agent that can list and vote on NNS proposals using an MCP server.
- Voting is done via delegated neurons with NNS permissions, showcasing real interaction with the Internet Computer.

#### Authentication Flow:
- A second example demonstrated wallet authentication via MCP, where a web front end enables the user to connect their wallet, sign a delegation, and send it to the MCP server, which then acts on their behalf.

---

### Challenges & Limitations:
- **Conflict Between Tools**: Multiple MCP servers can cause confusion if endpoints overlap.
- **Wallet Access**: Currently requires users to input keys, which is insecure and cumbersome.
- **Server-Sent Events**: ICP doesn’t fully support MCP’s preferred server-push architecture yet, though streaming HTTP is being explored.

---

## 💬 Open Discussion

### Decentralized Use Cases:
- Long mentioned that while Solana teams are exploring MCP for token transfers and blockchain interaction, his demo is one of the first real decentralized AI integrations with ICP.
- Potential seen in building customizable AI agents (e.g., autonomous voting, alerts).

### Tooling and Debugging:
- Debugging remains tricky, especially on Claude Desktop.
- There's a need for better logs and developer experience tools.

### Remote MCP Servers:
- Currently experimental, but teams are working on remote server support via HTTP(S).
- Tiago suggested adapting existing TypeScript frameworks using WASI polyfills and Azle for WASM compatibility.

### Future Outlook:
- A vision was shared for self-sovereign AI agents that are always available and act on a user's behalf (e.g., booking, messaging, decision-making).
- MCP could become a universal interface to apps, abstracting away traditional UIs.

### Model Size for Effective Agents:
- An 8B to 40B parameter model may suffice for effective MCP use, assuming tool count is manageable and interface specs are clear.

---

## 🛠 Next Steps & Resources
- Examples and boilerplates (e.g., MCP server template on ICP) were shared in the group.
- Continued development of developer onboarding material (e.g., Rust/TypeScript SDKs for MCP/LLM on ICP).
- Exploration of MCP as a potential inter-canister abstraction layer for on-chain agents.

---

## 🗓 Upcoming Calls & Topics

| Date     | Topic                                                                                                 | Presenter     |
|----------|-------------------------------------------------------------------------------------------------------|---------------|
| Apr 17   | AI4AI – Accelerated AI Infrastructure for ICP                                                                | Icarus        |
| Apr 24   | IConfucius – Fully On-Chain AI Agent on ICP                                                           | icpp (onicai) |
| May      | ANIMA demo ([link](https://forum.dfinity.org/t/introducing-the-llm-canister-deploy-ai-agents-with-a-few-lines-of-code/41424/35?u=patnorris)) | swift         |
| May (tbd)| Session on Efficient LLMs and DeepSeek                                                               |               |
| May (tbd)| Session on instruction limit                                                                          |               |
| Future   | Expert session on Active Inference implementations                                                    | Invite TBD    |
