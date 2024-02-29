# 2023.11.30 Meeting Summary - DeAI Working Group for the Internet Computer (ICP)

## Key Discussion Points

### Meeting Timeslot
- Establishing the best timeslot for the Working Group meetings.

### Decentralization and Marketplaces
- Exploration of how Singularity.Net is decentralizing their AI marketplace.
- Discussion on implementing a vector database within an IC canister.

### Vector Databases and Integration
- Possibility of using the FAISS library on IC, possibly with Kybra (Python) or icpp-pro (C++).
- Potential for Kybra to integrate icpp-pro for leveraging C++ libraries.

### Advanced Use Cases and Shared Projects
- Interest in running zkWASM on IC, potentially a good case for GPU subnet usage.
- Shared projects and resources for deep learning, including:
  - Tinygrad: A pure Python framework for deep learning.
  - Ring transformer: For distributing long sequences across devices.
  - Petals: Run LLMs at home, BitTorrent-style for faster fine-tuning and inference.
  - Tinyllama: Pretraining a 1.1B parameter Llama model on 3 trillion tokens.
  - Qwen: A chat and pretrained large language model by Alibaba Cloud.
  - Gorilla LLM: Trained to perform API calls, potential for running on IC.

### Goals
- Showcase capabilities and progress within and outside the IC community, including applications like gaming NPCs powered by models running in canisters.
- Focus on stable diffusion with smaller models and streamline the deployment of such models.

### Action Items
- Create a dashboard linked to Awesome IC for better discoverability and communication of projects and developments on IC.
- Develop a GPU subnet as a community effort.

## Dapps and ML Programming Highlights

### Dapps
- **ICGPT 6**: [CPU-inferencing LLM in a canister](https://icgpt.icpp.world/).
- **DeVinci App 6**: [WebGPU-inferencing LLM in a canister](https://x6occ-biaaa-aaaai-acqzq-cai.icp0.io/).

### ML Programming
- **C++ CDK 1**: [Integrating C++ dependencies and models](https://docs.icpp.world/index.html).
- **Rust Burn 2**: [ML framework developed in Rust](https://github.com/Tracel-AI/burn).
- **Tinygrad 1**: [ML framework in pure Python](https://github.com/tinygrad/tinygrad).

### Distributing AI Compute
- **RingAttention 1**: [Distributing computation of long sequences](https://arxiv.org/abs/2310.01889).
- **PetalsML**: [BitTorrent-style ML computation distribution](https://github.com/bigscience-workshop/petals).
- **Stable Horde**: [Distributed cluster for text and image generation](https://stablehorde.net/).

### Lightweight AI Models
- **TinyLlama 1.1B**: [Compact yet coherent LLM](https://github.com/jzhang38/TinyLlama).
- **Qwen 1.8B Chat**: [Compact LLM for chat applications](https://huggingface.co/Qwen/Qwen-1_8B-Chat).
- **SSD-1B**: [Distilled version of larger models for efficient use](https://huggingface.co/segmind/SSD-1B).
- **Gorilla LLM**: [LLM designed for making API calls](https://gorilla.cs.berkeley.edu/).

### LLM Structured Output
- Exploring methods to enable structured query output (e.g., JSON) consistently for LLMs, such as [LMQL, Guidance, Guardrails](https://github.com/guidance-ai/guidance).

