# 2025.11.20 Meeting Summary - DeAI Working Group for the Internet Computer (ICP)

## Short Version
This week’s DeAI Working Group call featured a live demo of LAIN, a decentralized AI-driven social/chat app on ICP, showcasing multi-channel conversations, friend-matching via embeddings, and hybrid use of the IC LLM canister plus DeepSeek. The discussion covered plans for client-side embedding generation, vector-database canisters, Odyssey video integration, and front-end challenges with Three.js on React Native. Participants also explored app distribution hurdles (Android/iOS), constraints of the IC LLM canister, and wishlist items such as an agent-optimized on-chain model and an MCP client library. The session concluded with a broader conversation on distributed vs. decentralized AI, edge hardware experiments, and emerging world-model concepts that point toward increasingly distributed and agentic AI systems.

### Links shared during the call:
* https://lain.io/
* https://github.com/dfinity/llm
* https://datasciencelearningcenter.substack.com/p/yann-lecuns-paper-on-creating-autonomous
* https://www.youtube.com/watch?v=ewDJpxQEGo4

## Long Version
This week’s session focused on a deep-dive demo of LAIN, a decentralized AI-powered social/chat app built on the Internet Computer (ICP), followed by a broader discussion on embeddings, agentic AI, distributed vs. decentralized architectures, front-end challenges, and hardware experiments.

## 1. LAIN Demo: Decentralized AI Social App

Vincenzo presented LAIN, an ICP-native social/chat application running on web and Android (React Native). It features multi-channel chat, friend discovery, user profiles stored on a canister backend, and multiple AI-driven channels. The AI component uses the IC LLM canister for most interactions but calls DeepSeek (via OpenRouter) for more advanced reasoning in the tech channel. The architecture keeps the backend simple (custom Rust canister + DB) and moves heavy AI work to the dedicated canister or external API.

## 2. AI Personalities, Embeddings & Friend Recommendations

Each channel uses the same model but with different system prompts to create distinct “personalities.” The app plans to generate per-user embeddings locally (via a lightweight client-side embedding model) and store them on-chain. By comparing these embeddings across users, the system will recommend new friends based on chat similarity. This avoids costly canister-side embedding generation and creates an emergent “social graph from taste profiles.” Eventually, embeddings from past conversations will shape AI responses to better match each user.

## 3. Embedding Pipeline & Vector Storage

Embeddings will be generated on-device, uploaded to the user’s section of the backend, and later stored in a vector-database canister for fast similarity search. The team discussed using fully client-side embedding models (e.g., “all-MiniLM” variants) and confirmed successful tests of vector DBs as canisters. The goal: a fully decentralized “taste graph” powering recommendations, personality alignment, and cross-user matching.

## 4. Odyssey Integration & Video Caching Strategy

Odyssey (YouTube frontend) integration is planned through tools rather than MCP. Two approaches were compared:
- Caching videos in a canister (fast lookup, less external API cost, but higher memory usage).
- On-demand external http_outcalls (lower memory, higher cost per call).
 Memory on ICP is relatively affordable, so a large local cache may be viable.

## 5. 3D Avatar Attempts & Front-end Challenges

A planned 3D avatar assistant was postponed due to incompatibilities between Three.js and React Native DOM. React Three Fiber partially worked on the web version but failed to build on mobile. Downgrading RN versions would introduce security issues, so the feature is deferred until the ecosystem stabilizes. A future PWA approach might simplify this.

## 6. App Distribution: Android, iOS & Native Issues

The Android app is days away from Google Play publication; beta-testing setup was slow.

iOS deployment is more restrictive and costly ($100/yr).

Internet Identity integration on native mobile is complicated due to deep linking and multi-window flows.

This reinforced the idea that a PWA might have been the smoother path.

## 7. IC LLM Canister: Constraints & Future

The official IC LLM canister remains easy to integrate but has strict limits:
 10-message chats, ~10 KB prompt, ~1000-token output.
 The open-sourcing timeline isn’t set yet, but improvements are planned. Despite limitations, the pattern for calling it is straightforward once understood.

## 8. Wishlist: Agent-Optimized Models & MCP Client Library

Two major ecosystem requests emerged:
- An agent-optimized on-chain model suited for planning, tool use, and multi-step workflows.

- MCP client library for ICP (in addition to the existing server library), enabling IC-hosted AI to call external MCP tools and APIs—unlocking richer agentic systems.

## 9. Hardware & Distributed AI Discussion

The group discussed:
- Jeff Geerling’s successful demo of an Intel GPU running on a Raspberry Pi to run a small LLM.

- A paper by Yann LeCun arguing for “autonomous models” with worldviews and distributed computation.

- The difference between decentralized vs. distributed AI, concluding these approaches will coexist:

- Distributed = scaling computation efficiently across hardware.

- Decentralized = governance, ownership, and trust minimization.

Participants explored how future AI systems may resemble entity-component architectures from gaming: models instantiated across many nodes at once, sharing worldview information, escalating tasks to higher-capacity reasoning layers when necessary, and optimizing for minimal computational cost.