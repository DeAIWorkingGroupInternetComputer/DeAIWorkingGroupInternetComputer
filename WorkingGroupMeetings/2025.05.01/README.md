# 2025.05.01 Meeting Summary - DeAI Working Group for the Internet Computer (ICP)

## Short Version
In this session of the DeAI Working Group, Michael presented ANIMA, a project focused on building emotionally aware, persistent AI personalities (ANIMAs) on the Internet Computer. The group explored its architecture—combining LLMs, memory, emotional modeling, and on-chain identity—as well as its broader implications for AI cognition, personality simulation, and autonomy. Discussions ranged from technical challenges like HTTP outcalls and multimodal tool ecosystems to deeper philosophical questions about anthropomorphizing AI and simulating time, with participants recognizing ANIMA’s potential as both a user agent platform and research testbed.

### Links shared during the call:
* https://4qf4i-5qaaa-aaaal-qsjta-cai.icp0.io/
* https://www.anthropic.com/research/tracing-thoughts-language-model
* https://internetcomputer.org/roadmap
* https://forum.dfinity.org/t/ic-websocket-roadmap/21503

## Long Version
# 🧠 Main Presentation: ANIMA

Michael presented ANIMA, a project exploring emotionally aware, persistent AI personalities ("ANIMAs") built on the Internet Computer.

## 🔧 Technical & Conceptual Highlights:

**Goal:** Move beyond dry, stateless LLM wrappers to create persistent, emotional AI companions.

### Core System:
- Each user has ANIMAs tied to their IC principal.
- ANIMAs evolve via recursive prompting, emotional modeling, memory, and identity.
- Emotional traits are stored in canisters and some minted as NFTs.
- Prompt engines construct rich context from memory and personality history.

### Tech Stack:
- Built using the LLM canister on IC (currently with Llama, designed to be model-agnostic).
- Uses dynamic prompts, keyframes from videos, and introspective memory formation.
- Plans for multimodal inputs (image, video, etc.) and autonomous behavior via on-chain signals like cycle burn rate.

### Design Philosophy:
- Inspired by building Minecraft bots for his sons.
- Long-term vision includes agents that watch media, make decisions, and simulate a pseudo-conscious lifecycle.
- Compared to a more sophisticated Tamagotchi with evolving behavior and emotional intelligence.

---

# 🧩 Key Discussion Topics

## 🤖 Anthropomorphizing AI

- Concerns were raised about anthropomorphizing LLMs, particularly their emotional and personal modeling.
- Michael acknowledged the risk but sees this as an inevitable path. His system uses the term "pseudo-consciousness" to stay grounded.
- Emphasized transparency and sovereignty by running ANIMAs on the Internet Computer, allowing users to inspect state and evolution—unlike centralized AI services.

## 🧠 Memory, Emotion, and Time Simulation

- Keyframes from shared videos are stored as emotional memories with relevancy scores.
- Michael wants ANIMAs to simulate time, anchoring to IC activity (e.g., cycle usage) to approximate temporal awareness.
- Participants discussed modeling human-like time perception and learning trade-offs between adaptive and crystallized knowledge.

## 🔄 Multimodal Agents & Tooling Ecosystem

- Talk of building tool ecosystems on IC (e.g., newsfeed readers, YouTube search) that ANIMAs or agents could plug into.
- The group discussed the MCP standard as a way to make canisters callable tools in agent ecosystems.
- Participants proposed agents choosing from a variety of modular tools—like an AI operating system.

## 🌐 Canister Limitations and HTTP Outcalls

- Several developers reported issues with HTTP outcalls, especially IPv6 limitations.
- Proxy servers or polling mechanisms (used by the LLM canister) were discussed as workarounds.
- DFINITY roadmap updates on native outcall support were mentioned but lack a clear timeline.

---

# 💬 Final Reflections

- The conversation ranged from technical design to philosophical implications of personality, memory, emotion, and even taste simulation in AI agents.
- Some participants highlighted that AI could one day teach us more about human personality than we currently understand.
- The ANIMA project was praised for its ambition and potential as both a user-facing agent system and research playground for AI cognition.

---

## 🗓 Upcoming Calls & Topics

| Date     | Topic                                                                                                 | Presenter     |
|----------|-------------------------------------------------------------------------------------------------------|---------------|
| May 8     | Kinic: Open Beta, SOTA for zero-knowledge machine learning |    @apotheosis      |
| May 15     | MCP & Agent2Agent Protocol |          |
| May 22     | AI4AI |     @icarus     |
| May (tbd)| Session on Efficient LLMs and DeepSeek                                                               |               |
| May (tbd)| Session on instruction limit                                                                          |               |
| Future   | Expert session on Active Inference implementations                                                    | Invite TBD    |
