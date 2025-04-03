# 2025.04.03 Meeting Summary - DeAI Working Group for the Internet Computer (ICP)

## Short Version
In this DeAI Working Group call, participants explored decentralized AI training via federated learning, emphasizing data ownership, on-chain verifiability, and incentive mechanisms. The discussion then shifted to future AI paradigms like active inference, reservoir computing, neuromorphic chips, and quantum machine learning—highlighting their potential for continuous learning, energy efficiency, and decentralization. A notable idea was using the Internet Computer as a distributed runtime for factor-graph-based inference. The session concluded with plans for upcoming demos and deep dives into model context protocol (MCP), AI hardware, and on-chain agents, reflecting growing interest in alternative AI architectures aligned with decentralized principles.

### Links shared during the call:
* https://docs.qubic.org/learn/upow/
* https://www.nvidia.com/en-us/products/workstations/dgx-spark/
* https://arxiv.org/html/2410.08892
* Kawa links
* https://research.google/blog/discovering-new-words-with-confidential-federated-analytics/
* https://arxiv.org/pdf/2204.05698
* https://arxiv.org/pdf/2401.10774
* https://biaslab.github.io/
* https://rxinfer.com/
* https://en.wikipedia.org/wiki/Von_Neumann_architecture
* https://en.wikipedia.org/wiki/Reservoir_computing
* 2024, An introduction to reservoir computing https://arxiv.org/html/2412.13212v1
* 2018, Reservoir Computing Universality With Stochastic Inputs, https://arxiv.org/pdf/1807.02621
* 2021, Next generation reservoir computing https://www.nature.com/articles/s41467-021-25801-2
* 2024, Backpropagation Algorithms and Reservoir Computing in Recurrent Neural Networks for the Forecasting of Complex Spatiotemporal Dynamics https://arxiv.org/pdf/1910.05266
* https://en.wikipedia.org/wiki/Spiking_neural_network
* https://en.wikipedia.org/wiki/Quantum_neural_network
* Technology Brief, Intel Labs’ Loihi 2 Neuromorphic Research Chip, ~2021: https://www.intel.com/content/www/us/en/research/neuromorphic-community.html
* 2024, World Economic Forum, Economy Blueprint Insight Report
* https://www.qureca.com/overview-of-quantum-initiatives-worldwide-2023/
* Natural Language, AI, and Quantum Computing in 2024 Research Ingredients and Directions in QNLP, https://arxiv.org/abs/2403.19758
* Quantum Self-Attention Neural Networks for Text Classification, https://arxiv.org/pdf/2205.05625
* https://en.wikipedia.org/wiki/Unconventional_computing
* 2022, Active Inference: The Free Energy Principle in Mind, Brain, and Behavior, https://direct.mit.edu/books/oa-monograph/5299/Active-InferenceThe-Free-Energy-Principle-in-Mind
* https://en.wikipedia.org/wiki/Action_(physics)
* Kullback–Leibler divergence
* Active inference ML street talk: https://www.youtube.com/watch?v=bk_xCikDUDQ 
* https://scholar.google.com/citations?hl=en&user=UalLlUQAAAAJ&view_op=list_works&sortby=pubdate

## Long Version

## Part 1: Federated Learning, On-Chain Training, and Verifiability of AI

### Decentralized Model Training via Federated Learning
- Federated learning was discussed as a method to train AI models on user devices (like mobile phones), preserving privacy since raw data stays local.
- Only anonymized model updates are shared and aggregated on-chain to build a global model.
- This could democratize AI model creation and offer on-chain rewards (e.g., tokens) to users contributing data or compute power.

### Data Ownership & Open Source Concerns
- There was a strong critique of current “open source” AI models: often the code is open, but the training datasets are not.
- It was emphasized that true openness also means having transparency and consent over the data used for training.

### Incentivization Layer & Blockchain Synergy
- Decentralized protocols can coordinate untrusted participants through trustless code and native token incentives.
- Participants could earn tokens based on the quality or amount of their contributed data or compute.

### Hardware and Scaling
- Mention of NVIDIA’s upcoming DGX Spark (~$4,000 device) as a key enabler for more people to train/run LLMs at home.
- Devices like this could significantly aid in federated learning or distributed inference efforts.

### Production-Readiness & Real-World Usage
- While federated learning holds promise, there were open questions about its production readiness in enterprise environments.
- Some participants were encountering the concept for the first time and expressed curiosity about proven use cases.

### Verifiability of Models & Accuracy
- Key concern: today’s systems lack mechanisms to verify what model is actually used at inference time.
- Proposal: using hashes of models and exposing them via endpoints (e.g., from WebAssembly canisters on ICP) to verify model identity and precision.

### Ideas
- Leverage on-chain rewards to encourage data sharing for AI training.
- Allow end users to verify model hashes to confirm correct model execution.
- Promote more transparency in AI service offerings (e.g., which model, what accuracy).
- Explore Medusa heads (layered fine-tuning for expert models) as a lightweight alternative to full LLM retraining.

## Part 2: Exploring Future AI Paradigms – Active Inference, Reservoir Computing, and Quantum AI

### Framing the Problem: Why Look Beyond Transformers?
- Today’s LLMs are powerful but computationally expensive, data-hungry, and largely static once deployed.
- There is a growing interest in alternative approaches that are:
  - More biologically inspired
  - Able to learn continuously
  - Better suited for low-power, real-time environments
  - Potentially more decentralizable by design

### Spotlight on Active Inference (AIF)

#### What It Is:
- A paradigm inspired by Bayesian brain theory and free energy principles in neuroscience.
- An agent-centric model where an entity learns and acts simultaneously to reduce its internal model’s uncertainty.

#### Key Concepts:
- Unlike traditional LLMs, active inference fuses training and inference.
- Agents learn on the fly from experience — no distinct training step.
- Core mechanism: factor graphs and message passing between variables and probabilistic functions.
- Tools/libraries mentioned: ForneyLab, RXInfer

#### Relevance to ICP:
- Idea: the Internet Computer could host a distributed factor graph, using canisters to represent nodes/factors and inter-canister messages for inference.
- This aligns with federated, privacy-preserving, and decentralized AI goals.

### Reservoir Computing (RC)

#### What It Is:
- Uses high-dimensional dynamic systems as reservoirs to transform inputs into rich representations.
- Inspired by how physical systems process information.
- A low-energy, real-time alternative to backprop-based training.

#### Current State:
- Still early-stage and largely experimental.
- One use case: solving the Traveling Salesman Problem with DNA molecules.
- Goal: tackle NP-hard problems more efficiently than classical computation.

#### Diverse Hardware:
- Implemented in a variety of physical substrates:
  - Photonic, electronic, spintronic, even biological systems
- This makes RC divergent and difficult to standardize, but ripe for radical innovation.

### Neuromorphic Computing
- Spiking neural networks (SNNs) mimic biological neurons more closely.
- More convergent research path than RC — grounded in neuroscience.
- Chips like Intel’s Loihi are already in development.
- Likely to reach practical applications earlier due to clear hardware paths and biological grounding.

### Quantum Computing & Quantum ML

#### Use Cases:
- Breaking classical encryption (e.g. Shor’s algorithm)
- Quantum Machine Learning: seen as a specialized co-processor for ML workloads
- Some researchers imagine hybrid models where quantum computers perform specific sub-tasks within classical ML pipelines.

#### Quantum Information Theory:
- Initially developed to describe physics, it is now being used for general-purpose computing.
- Could offer new information structures that classical systems cannot represent or compute efficiently.

### Discussion Highlights & Research Directions
- Multiple AI paradigms beyond transformers are gaining attention:
  - Active Inference
  - Reservoir Computing
  - Neuromorphic Chips
  - Quantum Co-processing
- There’s a growing belief that future decentralized AI systems might blend these approaches.
- The Internet Computer's architecture (message-passing, modularity, native parallelism) could align well with these paradigms — especially factor-graph-based systems.

## Part 3: Upcoming Calls & Topics

| Date      | Topic                                               | Lead           |
|-----------|-----------------------------------------------------|----------------|
| Apr 10    | Model Context Protocol (MCP) – First ICP Demo       | baolongt       |
| Apr 17    | AI4AI – Accelerated AI Infrastructure               | Icarus         |
| Apr 24    | IConfucius – Fully On-Chain AI Agent on ICP         | icpp (onicai)  |
| May (tbd) | Session on Efficient LLMs and DeepSeek              | Open           |
| Future    | Expert session on Active Inference implementations  | Invite TBD     |

---

## Closing Notes

- This session offered a refreshing change of perspective and broadened the group’s conceptual toolkit.
- There’s strong interest in:
  - Demos of unconventional AI systems
  - Sessions on efficient model architectures
  - Exploring how ICP can serve as a runtime for new AI computation models.