# 2025.10.23 Meeting Summary - DeAI Working Group for the Internet Computer (ICP)

## Short Version
Today’s DeAI Working Group call showcased major updates to ICP Coder, a Motoko-focused AI coding assistant integrated into Cursor and VS Code via the Model Context Protocol (MCP). The team presented a new hybrid Go + Python architecture, with Go handling authentication, user management, and API key issuance, while Python powers the data ingestion and RAG pipeline. They launched a public service with user registration, API keys, and an NPM package for easier IDE setup. The system now ingests Motoko repositories and documentation, embeds them with Sentence-Transformers, and serves context-aware completions through ChromaDB. Deployed on AWS, ICP Coder now supports Linux and macOS and plans to expand beyond Motoko to TypeScript and Rust. Upcoming improvements include advanced retrieval methods, payment integration, and rate-limiting for users, with continued work on performance, model accuracy, and developer usability.

### Links shared during the call:
* Simple instructions to give ICP Coder a try: https://github.com/Quantum3-Labs/icp-coder
* Quick demo here: https://www.loom.com/share/5d6ae7b8f4244d2b84438de7289ac1c0
* Swagger UI: https://icp-coder.q3labs.io/swagger/index.html
* Twitter: https://x.com/Q3Labs/status/1975834944363790818
* Rust sdk for MCP servers on ICP: https://github.com/ByteSmithLabs/ic-rmcp

## Long Version
## Topic

ICP Coder — a Motoko-focused AI coding assistant exposed as an MCP server and usable from Cursor/VS Code. Today’s update focused on architecture changes, auth, deployment, and a quick IDE demo.

## What’s new since last time
- Architecture refresh: Python → hybrid Go + Python
- Go: auth, user mgmt, API-key issuance, HTTP service.
- Python: data ingestion & RAG pipeline.
- Client packaging: Published NPM package so MCP clients can connect more easily.
- Auth flow: Public service with user registration + API keys.
- Docs: Swagger/OpenAPI for endpoints; updated README.

## System architecture (at a glance)
- Ingestion/RAG: Clone curated Motoko repos + docs → preprocess with Python → embeddings (Sentence-Transformers MiniLM) → store in ChromaDB.
- Serving path: MCP client (Cursor/VS Code) ↔ Go backend ↔ Python tools (retrieve context, generate code) ↔ return edits to IDE.
- MCP layer: Uses the Model Context Protocol; server exposes tools like get_motoko_context and code-generation actions.

## How to try it (today)
- Visit the hosted service, register, and obtain an API key.
- In Cursor/VS Code, add a custom MCP server entry (paste the provided JSON/snippet), install the published NPM package, and insert your API key.
- Ask Motoko/ICP questions in the IDE; the client will call server tools (you’ll see get_motoko_context etc.).

## Demo highlights
- Live Cursor session showed MCP tool calls firing, retrieval from the Motoko corpus, and agent-driven file edits (e.g., dfx.json, source updates).
- A rules/config file for task-specific prompting is being added to improve reliability.

## Current limitations / risks
- LLM backend: Using Gemini free tier (single account) — could hit token limits under load.
- RAG quality: Works, but the team wants more accuracy/latency tuning; benchmarks exist but more validation needed.

## Roadmap & ideas discussed
- RAG upgrades: larger/better sentence-transformers, multi-stage retrieval / chunking, and more advanced agentic RAG patterns.
- Language support: beyond Motoko — TypeScript, Rust, candid-to-full-app scaffolds (incl. Internet Identity integration).
- Operational controls: per-user rate limits/quotas; free tier now, later subscription with higher-tier models/features.
- Payments: likely handled in the Go backend first; potential ICP integration later.
- MCP SDKs: evaluate ICP-centric SDKs; compare with current general MCP stack and switch if beneficial.

## Deployment & infra notes
- Cloud: Deployed on AWS (team familiarity). Considering GCP internally later.
- Containers: Early images were large (embeddings + Chroma + corpora). Fixed via caching, pulling some components out, and better build steps.
- Cross-platform fixes: Chroma/packaging initially worked only on Windows; now Linux/macOS are supported.

## Q&A takeaways
- Public access? Yes — open-source codebase; hosted service is public (subject to LLM token limits).
Model choice in client? They’ll test different client LLMs with ICP Coder; no definitive “best” yet.
- Why Go? Performance & team experience for web services; Python remains for ML/RAG jobs.

## Action items / asks
- Try the hosted service, register, and connect from your IDE; share feedback on accuracy, latency, and model behavior.
- Next updates may cover TypeScript support, improved retrieval, and payment/rate-limit mechanics.
