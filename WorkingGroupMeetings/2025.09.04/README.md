# 2025.09.04 Meeting Summary - DeAI Working Group for the Internet Computer (ICP)

## Short Version
Today’s DeAI Working Group call featured Houman Shadab presenting Kinic, an ICP-based shared memory and semantic search layer for coordinating AI agents. He demoed how Kinic enables multi-agent collaboration (e.g., ChatGPT + Claude) through on-chain vector storage, semantic retrieval, and persistent memory, reducing repeated prompting and enabling overnight agent workflows. Discussion covered data quality, storage costs, computer vision use cases, verifiability via zero-knowledge proofs, and roadmap items like MCP integration and background APIs. Weekly Kinic workshops are running in New York, with a faucet available for first canisters. Next week’s session will feature Sanjeev on Active Inference.

### Links shared during the call:
* Kinic meetup in NY next Wednesday: https://luma.com/cp7kjm2c 
* https://github.com/hshadab/kinic-api
* www.kinic.io
* demo: https://www.youtube.com/watch?v=Ooipwo4TGXY
* BIPQuantum (law and AI on ICP): https://github.com/DeAIWorkingGroupInternetComputer/DeAIWorkingGroupInternetComputer/tree/main/WorkingGroupMeetings/2025.07.10

## Long Version
## Guest & Topic

* Presenter: Houman Shadab (law/tech background; former law professor turned startup founder).
* Topic: Kinic — an ICP-based shared memory + semantic search layer for coordinating AI agents.

## Demo & Core Idea

* Presented a working prototype of multi-agent collaboration (e.g., ChatGPT + Claude) using Kinic canister storage as a shared, persistent, on-chain memory and semantic search layer.
* Current API uses GUI automation (mouse/keyboard control via extension) to save websites/data to an ICP canister; a proper background API is planned.
* Semantic search over vectors lets agents (and humans) retrieve code/data by meaning (e.g., “greasy food” finds a pizza menu; natural-language queries can surface relevant code even if keywords aren’t present).

## Why it matters

* Enables agent-to-agent coordination, model diversity, and overnight workflows (e.g., agents review/build while you sleep), with persistent state that reduces repeated prompting and API/token costs.
* Useful for vibe coding and could generalize to other modalities (e.g., computer vision data).

## Q\&A Highlights

* Data quality: No built-in quality grading yet; users should combine Kinic with other tools for curation/validation.
* Modalities: Not limited to LLM text; can support other data types including CV.
* Autonomy: Demo shows semi-autonomous runs; goal is to support fully autonomous cloud agents that use the shared memory.
* Model/context needs: Not yet optimized for model size/context length; works with user-provided API keys and chosen models.
* Storage & cost: Canisters can hold several GB; multiple canisters per account are possible (costs scale with ICP burned). Vectorization increases size; precise cost per GB not provided. Potential to leverage new ICP BLOB storage when integrated.
* Security/safety (GUI control): Current mouse automation is deterministic scripting, not an AI making freeform OS decisions; risk is mainly accidental clicks until the background API lands.
* Verifiability / ZK: On-chain state provides auditable inputs/timepoints; can pair with ZK proofs (and/or on-chain compute) for end-to-end verifiable AI (“Kinic as mind, ZK/on-chain compute as body”).
* Protocols: Compatible with Google A2A; MCP integration is on the roadmap but starting simple first.

## Ecosystem Notes

* Workshops: Weekly Kinic workshops in NYC; moving to Internet Identity 2.0 / Google login to reduce onboarding friction. Presenter offered a token faucet (email him) so attendees can spin up a first canister.
* Potential synergies: Interest in potentially connecting funnAI (ICP AI agents) to Kinic for memory and gradual improvement.

## Next Session

* Expert talk by Sanjeev on Active Inference.

## Action Items

* Group members to try Kinic, share feedback, and NYC folks to consider attending the workshop.
* Explore potential integrations for shared memory
* Keep an eye on background API and BLOB storage integration for better autonomy and lower costs.