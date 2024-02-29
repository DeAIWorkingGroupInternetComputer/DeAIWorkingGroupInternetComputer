# 2023.11.23 Meeting Summary - DeAI Working Group for the Internet Computer (ICP)

## Introduction
This section captures a round of introductions from members of the AI on the Internet Computer (IC) working group. Each member shares their project/work and goals regarding AI on the IC, providing valuable context for their contributions and interests in the field.

### Projects and Goals

- Previously involved with other IC projects, now focusing on Uncensored Giants.
- Developing a marketplace for steps along the AI pipeline.
- Working on a Motoko library to train AI models on-chain for small to mid-sized models.
- Part of the DFINITY sdk team, contributing to [ic-mnist](https://github.com/smallstepman/ic-mnist).
- With a medical background, collaborates with data scientists to understand potential AI tools applications.
- Aiming to build a configurable chat assistant on IC, exploring decentralized options for LLMs, knowledge bases like vector stores, and skills/tools.
- Focused on running C/C++ based LLMs on the IC for inference purposes in the near term and training them on the IC in the longer term. Aims to run more extensive parameter LLMs for more generic use cases.

### Challenges and Lessons Learned

- **Technical Challenges**:
  - Memory limitations and max instructions per message.
  - Finding powerful enough models for specific applications.
  - Integrating vector stores and embedding on the IC.

### Wishlist for Project Development

- **Desired Features**:
  - Linear solvers and matrix decomposition functionalities for Motoko.
  - Deployment of Rust models and the implementation of a swarm of agents for asynchronous work.
  - Introduction of GPU subnets and considerations for federated learning.
  - Cost reductions by minimizing HTTP outcalls.
  - Improvements in GPU usage, higher limits for Orthogonal Persistence memory, and removal of max instructions per message limit.

### Administrative Notes

- **Group Goals**: The group aims to collaborate on advancing AI technology on the IC, sharing resources, benchmarks, and experiences.
- **Proposals**: Include recording meetings, maintaining a living document of needs, and establishing a dashboard for IC DeAI projects.
- **Meetings**: Weekly calls are proposed to be held every Thursday at 5pm UTC, lasting 30-60 minutes, focusing on project updates, news summaries, and action items.