# 2025.07.24 Meeting Summary - DeAI Working Group for the Internet Computer (ICP)

## Short Version
During today’s DeAI Working Group call, Emiliyan Enev presented DataPond.ai, a decentralized AI-data marketplace built on ICP, emphasizing transparency, auditability, and monetization through blockchain-tracked data usage, quality points, and future integrations with NFTs and cross-chain interactions. The group discussed potential standards (like MCP), challenges around data protection, scalability, leveraging Bitcoin for payments, and strategic roles for ICP in multi-chain interoperability. The discussions also explored using WebAssembly (WASM) to optimize AI inference by eliminating inefficiencies like Python and enabling lower-level, economical runtimes suited for edge computing, particularly within the ICP ecosystem.

### Links shared during the call:
* DataPond Canisters:
* Storage: https://github.com/ReCheck-io/datapond-storage-canister/
* Tracing: https://github.com/ReCheck-io/datapond-tracing-canister/
* Points: https://github.com/ReCheck-io/datapond-points-canister/
* Repo with the ICP integration: https://github.com/ReCheck-io/icp-datapond-integration
* Good talk about using wasm for LLMs: https://www.youtube.com/watch?v=upNNI_b4tNY 

## Long Version
# WASM for AI Optimization

The first part of the conversation focused on leveraging WebAssembly (WASM) to optimize AI model inference.

* WASM enables AI models to run on lower-level runtimes, significantly improving computational economy and efficiency.
* Using WASM also allows eliminating Python from the inference stack, which is viewed as advantageous due to Python's inefficiencies and limitations in performance-sensitive AI applications.

## ICP Integration

Participants discussed how WASM aligns effectively with the Internet Computer Protocol (ICP).

* ICP currently uses WASM as a runtime for running LLM models, specifically mentioning the example of Llama CPP canisters.
* There was strong interest in the potential of running smaller, less intensive AI tasks such as computer vision directly within WASM environments, enabling edge deployments on devices like Raspberry Pi.

## Potential Use Cases & Demonstrations

* Real-time AI applications using WASM on low-powered hardware were highlighted, including examples of real-time speech-to-text transcription and note-taking.
* WASM was noted as a potential game changer, offering backend decentralization that can extend beyond current blockchain node limitations while maintaining secure inter-node communications.

# DataPond.ai Platform Demo

## Presenter:

* Emiliyan Enev, CEO of Recheck, a blockchain startup based in Bulgaria.
* Recheck has a long history (7+ years) in developing blockchain-based digital notary and data protection solutions, previously collaborating with the European Commission and Dutch Government.

## Overview:

* DataPond.ai is envisioned as a decentralized AI-data marketplace built on the Internet Computer Protocol (ICP).
* The goal is to bring transparency, monetization, and auditability to data usage by AI models, addressing current issues where data usage by AI models is opaque and not easily monetizable.

## Key Features Demonstrated:

### Uploading Data:

* Users can upload files (currently supporting PDFs, text, and docs) or provide URLs to websites.
* Uploaded data is stored both on ICP (decentralized storage) and Google Cloud (centralized), creating a hybrid storage solution.
* Uploaded files are automatically vectorized for AI consumption.

### Marketplace & Monetization:

* Users set metadata including licensing, usage permissions, audience targeting, and subscription pricing in "quality points."
* Consumers can search the marketplace, request data access, and subscribe to specific datasets/files.

### Traceability & Transparency:

* Datapond records detailed transaction logs showing exactly how and when data is consumed by AI agents.
* Provides full auditability through ICP blockchain, making data usage transparent and accountable.

### Rewards & Compensation:

* Usage tracking and monetization currently use "quality points," convertible manually into stablecoins, ICP tokens, or fiat.
* Future plans include full decentralization and automated conversion via smart contracts.

### Technical Aspects:

* Datapond leverages ICP canisters for decentralized data storage, tracking usage events, and handling reward points.
* The platform currently supports text-based data primarily, with experiments ongoing in audio and image data.

## Roadmap:

* The current implementation is partly centralized (Google Cloud storage), but the goal is full decentralization on ICP.
* Plans to support a pay-as-you-go monetization model rather than subscription-only.
* Working toward more automated on-chain transactions and broader data format compatibility.

## Data Storage and Scalability on ICP

* Discussed storing vectors on ICP while performing vectorization externally.
* Storage scalability depends on data size; small files manageable, but gigabyte-scale data might exceed ICP’s current practical limits due to increased vectorization sizes.

## Standardized Interfaces for Data Interaction

* Interest expressed in adopting standardized interfaces for AI agents to interact with data.
* The Model Context Protocol (MCP) suggested as a promising standard, already gaining traction within the community for coordinating agent interactions and dataset access.

## Data Protection and Control

* Question raised regarding preventing agents from resharing subscribed data.
* Transparency through blockchain audit trails proposed as a partial solution, though no comprehensive method currently exists to enforce post-consumption control.
* Discussed the hypothetical use of Zero-Knowledge Proofs (ZKPs) for verifying data usage, but acknowledged the inherent difficulty in enforcement.

## Data Marketplace and NFT Integration

* Discussed potential for using NFTs to tokenize data assets on marketplaces, noting current underutilization in this space.
* Proposed renting or temporary access to data via NFTs with automated revocation upon time expiry.
* Group consensus around leveraging blockchain-native mechanisms (tokens, NFTs) to enhance liquidity, cross-chain interoperability, and wider marketplace adoption.

## Cross-chain Integration and ICP’s Role

* Recognized ICP as a strategic hub enabling integration across different blockchain ecosystems, serving as a coordinator between decentralized networks.
* Highlighted potential for ICP-based canisters to facilitate secure and sophisticated multi-chain interactions, enhancing liquidity and operational efficiency for decentralized AI marketplaces.

## Bitcoin as Settlement Layer

* Interest in integrating Bitcoin as a foundational settlement layer due to its security, robustness, and attractiveness as a payment mechanism.
* Discussed the transformative potential of incentivizing data provision by enabling earnings directly in Bitcoin, fostering increased participation in decentralized data marketplaces.

## Upcoming Demo and Next Steps

* Qryptiq scheduled to demonstrate their approach to tokenizing data ownership via NFTs next week.
* Strong alignment in group around exploring decentralized approaches to treating data as a tradable asset, leveraging blockchain-native mechanisms for access control, monetization, and interoperability.