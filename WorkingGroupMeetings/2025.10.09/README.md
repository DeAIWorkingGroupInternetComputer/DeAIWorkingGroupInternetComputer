# 2025.10.09 Meeting Summary - DeAI Working Group for the Internet Computer (ICP)

## Short Version
The session featured Gian and Diego presenting ICP Coder, an open-source Motoko-focused AI coding assistant that integrates with VS Code/Cursor via an MCP server and leverages RAG over curated Motoko documentation and code. It currently runs locally using Chroma as the vector database and Google Gemini as the LLM, offering semantic retrieval and context-aware code generation. The team plans to host a Web2 version soon and later migrate to ICP canisters once technical constraints allow. Discussion covered database scalability, embedding model trade-offs, and future directions like Agentic RAG, configurable sentence transformers, and multi-language support (Rust, TypeScript, Python). The demo successfully showcased live ingestion and retrieval, impressing participants with its hands-on, transparent setup.

### Links shared during the call:
* ICP Coder forum thread: https://forum.dfinity.org/t/icp-coder-ai-assistant-for-motoko-code-generation/57881/3
* ICP Coder repo: https://github.com/DiegoFloresWenHao/ICP_Coder
* Paper on RAG: https://arxiv.org/abs/2507.18515

## Long Version
## Presenters:

Gian + Diego (developers of ICP Coder)
**Focus:** Demonstration of ICP Coder, a Motoko-focused AI coding assistant, exposed as an MCP server and integrated into VS Code/Cursor.

## 🧩 Overview

ICP Coder is an AI coding assistant designed to help developers write and understand Motoko, the Internet Computer’s native language. It uses Retrieval-Augmented Generation (RAG) over a curated Motoko code and documentation corpus to provide accurate, context-aware code suggestions inside an IDE.

## ⚙️ Architecture & Setup

**Environment:**

* Runs locally with Cursor or VS Code, connected to a local MCP server.
* Uses Chroma as the vector database for semantic search and context retrieval.
* LLM backend: Google Gemini, chosen for its free tier and large context window (>1M tokens).

**MCP Tools:**

* get_motoko_context: retrieves relevant chunks of code/documentation.
* generate_motoko_code: generates new code based on retrieved context.

**Pipeline:**

* Ingests ~100 open-source Motoko projects plus official documentation.
* Focuses on .mo files.
* Applies chunking, vector embedding, and metadata tagging.
* Prioritizes official docs during retrieval.

## 🧮 RAG & Vector Database Design

**Database:** Chroma

* Chosen for being open-source, proven in other LLM projects, and cost-free.
* Alternatives (e.g., PostgreSQL with pgvector) considered viable long term.
* Limitation: RAG performance drops with very large databases → careful scaling needed.

**Sentence Transformer:**

* Current: a MiniLM model (lightweight, fast).
* Potential upgrade: Stella Dongchang 1.5B for higher precision (but higher compute).
* Trade-off: ~minutes vs. hours for vectorization.
* Lesson: balancing embedding quality, compute cost, and query latency is key.

**Retrieval:**

* Typical query returns ~10 code samples (~10k–15k tokens per Gemini call).
* Context retrieval accuracy already high; hybrid search (FTS + vector) under consideration.

## 🧱 Hosting Roadmap

**Current:** local-only prototype.
**Next few weeks:**

* Host server + vector DB (Web2 stack, likely AWS).
* Provide API key registration + hosted endpoint.
* Later move toward canister-hosted version on ICP once performance constraints allow.

Discussion emphasized: current ICP canisters can support small vector DBs, but large-scale RAG hosting still requires off-chain or hybrid setups.

## 🧭 Future Directions

**Agentic RAG:**

* Use an LLM to autonomously evaluate, refine, or re-query retrieved results.
* Could be a “Pro” tier or premium option for advanced users.

**Fine-Tuning vs. RAG:**

* Fine-tuning (e.g., instruction tuning) considered but deprioritized:
* Too computationally expensive.
* Current frontier models (Gemini, Claude, GPT-4) are “smart enough” when paired with good RAG.
* Plan: focus on improving retrieval quality, metadata, and pipeline efficiency.

**Custom Transformers & Configurable UX:**

* Users may choose their preferred sentence transformer depending on local hardware.
* Hosted setup will offer toggleable configurations for embedding models and retrieval parameters.

**Multi-language Expansion:**

* Potential for Rust, TypeScript, and Python support.
* Current Motoko focus could be extended to Rust canister generation — early tests successful but limited.

## 💬 Q&A Highlights

**Why Chroma?**

* Open-source, flexible, proven, avoids external API costs, large capacity.

**ICP Hosting Feasibility:**

* Current ICP vector DBs exist but limited by canister memory and round-trip latency.
* Hybrid off-chain or adjacent ICP compute solutions are near-term targets.

**Token Usage:**

* Each RAG call consumes roughly 10k–15k tokens (input + output combined).

**Integration Ideas:**

* Could be combined with Claude Desktop or Cursor AI to augment their internal context.
* Possible business model: freemium (open-source + premium hosted tier).
* Could allow ingestion of user’s own codebases to extend the assistant’s context.

## 🧩 Discussion with Participants

Participants suggested using ICP Coder for:

* Personal or team codebase context ingestion.
* Learning Motoko concepts (e.g., scaffolding dfx projects, generating canisters).
* Translating code between Motoko and Rust.
* Lowering entry barriers for new developers in the ICP ecosystem.

Some users noted that Caffeine AI (DFINITY’s new initiative) dominated recent events and that tools like ICP Coder could complement Caffeine by supporting more technical developer onboarding.

## 🏁 Closing

The team plans to continue improving the project, benchmark the hosted version soon, and later re-demo once the hosted MCP endpoint is available. The demo impressed participants by showing the full ingestion and retrieval flow live, “from scratch”.