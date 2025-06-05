# 2025.06.05 Meeting Summary - DeAI Working Group for the Internet Computer (ICP)

## Short Version
The meeting introduced new projects, including an AI-driven wallet and a spam prevention solution leveraging ICP security features. Highlights from the World Computer Summit emphasized Caffeine AI’s transformative potential, with discussions covering infrastructure costs, decentralized AI integration, and security enhancements through AI-driven auditing. The group recognized the need for open-sourcing ICP-specific training datasets, improving hardware optimization through SIMD and WASI, and collecting structured developer feedback to accurately gauge demand and capabilities, proposing clear next steps for collaborative research and community-driven initiatives.

### Links shared during the call:
* https://o3de.org/
* https://github.com/ByteSmithLabs/ic-rmcp/tree/main
* https://ladybird.org/
* Unsloth.ai
* https://en.wikichip.org/wiki/x86/avx512_vnni
* https://en.wikipedia.org/wiki/AVX-512
* https://edc.intel.com/content/www/us/en/design/ipla/software-development-platforms/client/platforms/alder-lake-desktop/12th-generation-intel-core-processors-datasheet-volume-1-of-2/006/intel-avx2-vector-neural-network-instructions-avx2-vnni/

## Long Version

## New Members & Projects Introduced

- **New Wallet Project:** Yehia introduced his abstract wallet project, featuring AI-driven financial consultancy capabilities. He expressed interest in migrating from AWS microservices to ICP due to decentralization advantages.

- **Spam Prevention Project:** Pineapple described his ICP-funded project focused on tackling crypto-related spam on platforms like Twitter and YouTube, leveraging AI heuristics for robust filtering. He highlighted the security benefits of ICP and vetKD (vet keys).

- **Open 3D Engine (O3DE):**
  - Jupes presented his early-stage project using O3DE, highlighting its use beyond gaming for robotics and AI-driven warehouse simulations.
  - The Atom Renderer within O3DE was praised for high performance and potential superiority over Unreal Engine and Unity in modularity and modern design.

- **MCP Server Development:**
  - Long's team is actively developing an MCP server running inside ICP canisters, though currently in early stages with breaking changes anticipated soon. He recommends awaiting a stable release in a few weeks.

## World Computer Summit Recap

- **Patrick and Kawa** shared insights from the Zurich event.
  - **Attendance:** High (500-1000? attendees), event felt crowded.
  - **Keynotes:** Dominic Williams showcased "Caffeine AI," demonstrating easy deployment of AI-generated canisters.
  - **Feedback:** A multi-day event was recommended for deeper networking.

### Content Tracks:
- **Business Track:** Discussions felt somewhat repetitive (decentralization, sovereignty).
- **Technical/Ecosystem Track:** Noted as richer in content, including AI, DeFi (BTC-Fi), and chain fusion.

## Caffeine AI Insights and Discussions

- Caffeine AI was highlighted as potentially transformative, simplifying canister deployment.
- Questions raised around:
  - On-chain vs off-chain AI processing.
  - Security and code management.
  - Pricing strategy.
- Group members see potential for Caffeine AI to serve both beginner users and developers, possibly becoming a productivity tool within ICP.
- Interest expressed in integrating decentralized AI standards (MCP, Agent2Agent protocol) with Caffeine AI, fostering easier deployments for broader adoption.

## Model Costs and Infrastructure Planning

- Ongoing concern about the increasing costs of prompting frontier AI models.
- Consideration of adopting open-source models approximately a year behind frontier models as a cost-effective strategy.
- Planning for multi-model service platforms within the ICP ecosystem, recognizing the need for clear structure around how different models handle various tasks.

## Security Considerations

- Proposal of specialized models or modules that enhance security by auditing code, specifically looking for vulnerabilities related to deploying or upgrading canisters on the ICP.
- Suggestion to integrate decentralized "gatekeeper" services using AI models to verify and manage code quality, credentials, and identity management.

## Decentralization and Self-Hosted AI

- Acknowledgment that fully on-chain AI text generation isn't economically feasible yet due to computational cost.
- Interest in decentralized solutions where users can self-host open-source models, integrating easily with back-end services provided by platforms like Caffeine AI.

## Hardware Optimizations

- Strong emphasis placed on leveraging hardware optimizations (e.g., SIMD instructions, AMD-specific extensions) for significant computational efficiency gains (potentially 75% reduction in instructions and up to 8X speedups).
- Preliminary research into adapting the WASM interpreter and leveraging hardware-specific optimizations via WASI routes.
- Recognition of the challenge of determinism when integrating hardware optimizations into the ICP, with the necessity for thorough testing by DFINITY.

## ICP-Specific AI Workloads and Training

- Proposal to open-source training datasets and procedures (particularly for Motoko) to allow the community to fine-tune their own models easily, thus fostering a more diverse and adaptable model ecosystem.
- Discussion of tools and frameworks (e.g., Open-Assistant) for training and fine-tuning models, particularly composable models suitable for ICP-specific tasks.

## Testing Demand and Model Capability

- Concerns raised that current limited deployment of single models as inference servers may not accurately represent true market demand for decentralized AI.
- Suggestion to organize community surveys or structured feedback from developers on the current inference capabilities versus real-world needs and to communicate these to inform future investments.

## Action Items and Initiatives Proposed

- **Community Feedback Initiative:** Plan to conduct a developer-focused survey or structured feedback collection to assess AI capabilities versus needs.
- **Hardware Research Collaboration:** Further investigate hardware acceleration and WASM interpreter optimizations, potentially leading to proposals or pull requests to DFINITY’s ICP core protocol.
- **Open-Source Contributions:** Encourage and possibly initiate open-source publication of datasets and fine-tuning procedures for ICP-specific AI models, enhancing community-driven model development.

## Next Steps

- Coordinate a follow-up discussion in upcoming sessions to refine the feedback initiative and discuss preliminary results.
- Consolidate hardware optimization research into a dedicated repository or spreadsheet for shared community access and transparency.
