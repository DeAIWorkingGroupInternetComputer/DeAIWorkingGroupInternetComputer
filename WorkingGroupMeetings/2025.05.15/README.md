# 2025.05.15 Meeting Summary - DeAI Working Group for the Internet Computer (ICP)

## Short Version
The session covered developments in integrating Model Context Protocol (MCP) with ICP, demonstrating a working prototype on ICP canisters and plans for an MCP SDK, while highlighting challenges such as ICP's 2MB HTTP call limit and MCP's complex streaming protocol. An overview of Google's Agent-to-Agent (A2A) Protocol was provided, noting its standardized inter-agent communication and potential complementarity or competition with MCP, as well as straightforward ICP integration possibilities. The meeting concluded with community suggestions for future sessions, including Vibe Coding and a hardware-focused presentation by Icarus next week on Accelerated Infrastructure for AI on ICP.

### Links shared during the call:
* https://github.com/okoyfoeciov/test-mcp-server-on-ic-canister
* https://www.youtube.com/watch?v=UBuS19pkEno
* https://github.com/modelcontextprotocol/typescript-sdk/issues/220
* https://internetcomputer.org/docs/building-apps/network-features/using-http/http-certification/serving-json-over-http
* https://github.com/modelcontextprotocol/rust-sdk
* https://github.com/modelcontextprotocol/modelcontextprotocol/issues/205
* https://developers.googleblog.com/en/a2a-a-new-era-of-agent-interoperability/
* https://github.com/google/A2A
* https://google.github.io/A2A/specification/#5-agent-discovery-the-agent-card
* https://google.github.io/A2A/topics/key-concepts/#core-actors
* https://google.github.io/A2A/topics/a2a-and-mcp/

## Long Version
📌 **Main Topics**

### 1. Introduction and Welcome
- Welcomed new member Keyvan, an AI researcher previously associated with Ben Goertzel's OpenCog lab and early ICP contributor.
- Invited community contributions for future calls, emphasizing the openness of the group to new ideas and participation.

### 2. Model Context Protocol (MCP) on ICP
- Long presented recent developments integrating MCP with ICP.
- Demonstrated a working prototype of MCP servers running on ICP canisters, allowing AI interactions via HTTP handlers.
- Discussed creating an MCP SDK to simplify canister deployment and interaction via ICP, built in collaboration with a friend specializing in AI development.
- **Identified challenges including:**
  - The limitation of ICP HTTP calls (currently 2MB) potentially restricting extensive context sharing.
  - Current complexity of MCP’s Server-Sent Events (SSE) streaming; preference expressed for a simpler streaming protocol.
- Discussed broader MCP adoption, current criticism, and integration with Google's Agent-to-Agent (A2A) Protocol.

### 3. Agent-to-Agent (A2A) Protocol Overview
- Patrick provided an overview of Google’s new A2A protocol, designed to enable decentralized communication between autonomous agents across different organizations.
- **Key A2A features include:**
  - Standardized communication (JSON-RPC via HTTPS).
  - Discoverability through agent cards describing capabilities and skills.
  - Compatibility with existing agent frameworks (e.g., LangGraph, CrewAI).
- **Discussed complementarity and potential competition between MCP and A2A:**
  - MCP primarily for agent-tool integrations.
  - A2A designed for inter-agent communication across different infrastructures.
- Speculated potential future convergence or competition between the two standards.
- Identified ICP compatibility with A2A, noting straightforward integration possibilities (HTTP polling, request-response), but flagged streaming and push notifications as areas for further exploration.

### 🗣️ Community Engagement & Future Topics
- Opened the floor for topic suggestions:
  - Potential future session on Vibe Coding (initiated by a group member).
  - Next week's session (earlier by 3 hours) will be led by Icarus on Accelerated Infrastructure for AI on ICP (hardware-focused).

---

## 🗓 Upcoming Calls & Topics

| Date     | Topic                                                                                                 | Presenter     |
|----------|-------------------------------------------------------------------------------------------------------|---------------|
| May 22     | AI4AI |     @icarus     |
| May (tbd)| Session on Efficient LLMs and DeepSeek                                                               |               |
| May (tbd)| Session on instruction limit                                                                          |               |
| Future   | Expert session on Active Inference implementations                                                    | Invite TBD    |
