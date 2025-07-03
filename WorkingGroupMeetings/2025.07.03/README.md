# 2025.07.03 Meeting Summary - DeAI Working Group for the Internet Computer (ICP)

## Short Version
In today’s DeAI Working Group call for the Internet Computer, Long gave an extensive live demo of the MCP server running on IC, showing how AI agents can perform wallet operations (like balance checks, ICP transfers, and transaction histories) via HTTP gateways, while also discussing current authentication challenges. He highlighted progress on multi-chain wallet support with threshold signing for Bitcoin and Ethereum. Meanwhile, Jupes shared his work on running LLMs on a small Kubernetes Raspberry Pi cluster to power decentralized virtual AI “residents” in a simulation-style metaverse. The group explored ideas around integrating these with personal MCP servers, discussed potential for AI to propose rules in such environments, and Long asked for further feedback on the MCP SDK by the community.

### Links shared during the call:
* https://github.com/ByteSmithLabs/mcp-examples
* share feedback on MCP SDK with Long on X: https://x.com/long2408
* https://github.com/ilbertt/ic-react-native-jwt-auth?tab=readme-ov-file#how-it-works
* https://github.com/nobodywho-ooo/nobodywho
* https://www.media.mit.edu/publications/your-brain-on-chatgpt/
* https://arxiv.org/abs/2506.08872

## Long Version
The call featured an extensive live demo by Long, showcasing the latest progress on the MCP (Multi-Chain Protocol) server running on the IC.

He demonstrated how AI agents can interact with MCP servers to perform wallet operations, including checking balances, sending ICP tokens, and retrieving transaction histories, all orchestrated via AI tool definitions and the HTTP gateway.  

Examples included integrating with IC ledger, showing stable memory storage for API keys, and leveraging the VS Code Copilot integration to add and test MCP server tools directly.

There was also a technical discussion about authentication challenges:

- Currently, because the HTTP gateway can't validate principals, there is no native way to confirm who is calling the MCP server.
- The group explored possibilities like OAuth, JWT tokens, or future improvements, and noted limitations with using API keys alone.

Long also previewed progress on supporting multi-chain wallets, using threshold signing to manage Bitcoin and Ethereum keys, although transfers on these chains still face technical hurdles. He plans to keep developing this to enable a canister-run multi-chain wallet controlled by AI.

Additional ideas included:

- How personal MCP servers could act as plugins for Caffeine AI or other AI tools, providing self-hosted agent utilities (like wallets or other tools).
- How to eventually tie these into decentralized metaverse or game-like environments, where AI agents (or “AI residents”) interact socially and economically, for example by giving out or managing tokens.

Jupes shared updates on his experimental project to run LLMs on a small Kubernetes Raspberry Pi cluster to serve as endpoints for interactive virtual residents. He described a vision of building decentralized, simulation-based metaverses with AI-controlled robots that could exist virtually and potentially be built in the physical world.

The group discussed longer-term ideas like creating an AI “observer” resident to propose the economic and physical laws of such a simulated metaverse.

Finally, Long encouraged everyone to test his MCP SDK and provide feedback, ideally by opening issues or sending direct messages on X (Twitter), though he mentioned possibly creating a dedicated handle for the project.

✅ **Action items:**
- Try out the MCP SDK, give feedback via issues or DM on X.

**Consider future agenda slots:**
- A dedicated walkthrough of Jupes’ decentralized metaverse / AI residents project.
- More discussion on secure authentication strategies for MCP over HTTP gateways.