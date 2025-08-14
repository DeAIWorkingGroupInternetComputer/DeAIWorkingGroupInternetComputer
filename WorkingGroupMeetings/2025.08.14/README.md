# 2025.08.14 Meeting Summary - DeAI Working Group for the Internet Computer (ICP)

## Short Version
The call focused on recent progress in building MCP (Model Context Protocol) on the Internet Computer, including OAuth 2.0 support in the Rust SDK for secure, multi-user authentication via Internet Identity. This enables use cases like AI-assisted crypto wallets and multi-user wallet management. Discussions covered deploying MCP servers on-chain to improve trust through WASM hash verification, creating a trustless MCP Server Marketplace, and potential integration with existing ICP canisters using auto-generated MCP interfaces. Additional discussions included running AI models as WASM modules in canisters, and unlocking decentralized AI workflows with ICP’s large memory capacity.

### Links shared during the call:
* https://github.com/ByteSmithLabs/ic-rmcp/tree/main/examples/clock
* https://github.com/ByteSmithLabs/mcp-examples/tree/main/token-transferring
* https://forum.dfinity.org/t/a-trustless-app-store-for-ai-agent-apps/55492
* https://www.youtube.com/watch?v=Ts42JTye-AI

## Long Version
## Main Topic – MCP Servers on ICP with OAuth 2.0 Support

### Hackathon Update
Work is underway on an MCP (Model Context Protocol) App Store, developed in four phases. Earlier phases included an OAuth canister and a Motoko SDK for MCP. The current phase focuses on the App Store UI, auditing process, and deployment of MCP servers on-chain.

### Rust SDK Progress
- Originally used API key auth via HTTP headers — fast for prototyping but insecure and outside the MCP spec.
- Now supports OAuth 2.0 per the official MCP spec, with full client–server–authorization server flow.
- Demo showed MCP authentication in VS Code using Internet Identity, granting multi-user server support and secure token revocation.

**Use Cases Enabled:** Multi-user wallet management servers, AI-assisted crypto wallets, token transfers with separate subaccounts per user.

---

## Security & Trust Discussion
- Moving MCP servers on-chain can mitigate spoofing, tampering, and hidden code changes.
- Proposal for a trustless MCP Server Marketplace: each server version tied to a WASM hash, with open-source verification or trusted auditing.
- Even without open source, publishing the WASM hash allows proof of code immutability.

---

## Integration & Tooling
- API keys still useful for self-hosted/private MCP servers.
- Potential to wrap existing ICP canisters (e.g., OpenChat) with MCP interfaces. Challenges include identity/auth alignment between OAuth and app-specific logins.
- Plugins could auto-generate MCP integration code from a canister’s Candid interface.
- Caffeine AI could help generate Motoko MCP servers (frontend not required).
- Getting started: learn MCP request lifecycle, review SDK examples (e.g., counter server), override server/tool methods, then expand to custom use cases.

---

## Future Directions & Experiments
- Running AI models as WASM modules inside canisters (WASI) for language-agnostic model hosting.
- Example: image-to-3D model conversion on-chain to leverage ICP’s large memory capacity.
- Architecture could involve a Motoko canister interfacing with a dedicated AI-model canister (e.g., using ported Llama.cpp).

---

## Key Takeaways
- OAuth 2.0 support in the Rust SDK makes ICP MCP servers fully spec-compliant and compatible with existing MCP clients.
- On-chain MCP servers + WASM hash verification open the door to trustless AI service marketplaces.
- Identity integration remains a challenge for wrapping existing canisters, but plugins and standardization could simplify this.
- Running AI models directly in ICP canisters is technically possible and could unlock unique decentralized AI workflows.