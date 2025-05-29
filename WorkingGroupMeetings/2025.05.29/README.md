# 2025.05.29 Meeting Summary - DeAI Working Group for the Internet Computer (ICP)

## Short Version
The DeAI Working Group discussed and advanced a hardware-runtime comparison framework for AI accelerators. Key updates included runtime benchmarking (TensorRT, vLLM, Modular), open model selection (LLaMA, Mistral), quantization pipelines via GGUF, and tools for format conversion and model interoperability. Real-world experiments with 3B–7B quantized models showed promise for on-device inference, supporting IC-compatible AI agent deployment across browser, edge, and mobile environments.

### Links shared during the call:
* https://docs.google.com/spreadsheets/d/1a-NzZeh6D9smxovW7ByYOx7Ls1tRqBJyaS9gXVzRy-Y/edit?gid=0#gid=0
* https://docs.google.com/document/d/1IbaQqDzyXbLetGtLzuFWdv1u7vl8LKtEDaOissv6Czo/edit?tab=t.0#heading=h.nt6jx1d33gi8
* https://www.techpowerup.com/
* https://github.com/InternLM/lmdeploy

## Long Version
## 🔄 Cross-Chain Yield Vaults & DeFi Integration
An initial topic was integrating cross-chain DeFi capabilities into browser-native apps using oisy Wallet with chain fusion.  
This unlocks Ethereum-based asset use (e.g., Uniswap LP tokens) for paying for access to apps on IC, entirely via browser wallets, without plugins.  
Potential implications for decentralized AI, including funding AI workloads via yield farming mechanisms, were highlighted.

## 🧩 Godot + AI UX Integration
Exploration of Godot-based UI rendering for AI interfaces, potentially improving responsiveness and animation quality when accessing AI features.

## 🌍 Wallet Ecosystem Observations
Fragmentation across multichain wallets (Talisman, Math Wallet, etc.) was discussed.  
oisy Wallet was noted as a promising project for truly cross-chain support, with Polkadot integration planned.

## 📊 Hardware + Runtime Evaluation Framework
Ongoing effort to document and compare AI accelerator hardware (NVIDIA, AMD, Tenstorrent, etc.) in a shared spreadsheet:  
Columns include: Power draw, nominal price, INT4/INT8/FP16 peak performance, and availability.  
Sources include TechPowerUp and vendor sites.  
Call participants were encouraged to contribute data, especially for lesser-known chips like Esperanto, D-Matrix, and AMD MI300-series.

## 🧠 AI Inference Runtime Landscape
Initial comparison of software stacks:
- NVIDIA’s TensorRT, BLLM, LLMD, and Modular’s Max engine.
- Highlighted: Modular is hardware-agnostic and easy to install on consumer GPUs (e.g., 4080).
- LMDeploy.ai was added as a highly recommended runtime.
- vLLM has recently improved context handling, but NVIDIA’s stack still outperforms it due to optimized CPU offloading.

## 📚 Model Selection & Benchmarking
Emphasis on open or open-base models (e.g., LLaMA, Mistral, Qwen) for initial testing and deployment on IC.  
Discussion around leveraging community benchmarks (e.g., HuggingFace, LMSYS, LLM-Rating) to shortlist performant models.  
Participants supported the idea of defining a set of candidate models (~70B max) to evaluate systematically.

## 🧪 Evaluation Criteria & Model Families
Key selection factors:
- Out-of-the-box support by runtime  
- Architecture compatibility (e.g., LLaMA standard)  
- Update frequency and institutional backing (e.g., Meta, Alibaba)  
- Fit for target task (chat, reasoning, math)  

Participants acknowledged that support often extends beyond listed models due to easy format conversion.

## 🧠 LLM Training & Quantization Pipeline
Ongoing work on English-German LLM training (bit-based models).  
Training performed using Intel Xeon with 3090 GPUs, using Wikitext, OS Wiki dumps, and Common Crawl-based datasets.

Quantization pipeline:
- Models first converted to FP16 with `transformers.convert_graph_to_onnx`.
- Then quantized to INT8 or INT4 via GGUF + `llama.cpp`.

## 🧪 Evaluation Tools & Techniques
Prompt layer-based metrics (e.g., truthfulness, factuality) using:
- Open LLM Leaderboard  
- LLM Rating Arena  
- MT Bench  
- TruthfulQA, HellaSwag, and MMLU

Custom eval: Participants encouraged use of Tonic.ai, EvalGen, and LangSmith for fine-tuned evals of domain-specific agents or models.

## 🔍 Model Interoperability & Prompt Translation
Prompt translators between model families discussed:
- OpenDevin and LLM Compiler projects offer adaptable prompt translators between Claude, GPT, Mistral, etc.
- Example: translate system + user prompt for GPT-style model into Anthropic format and vice versa.

## 🔀 Format Conversion Tools
Universal checkpoint and tokenizer format tools noted:
- `transformers-cli convert` for tokenizer porting  
- `gguf.py` for quantization-ready checkpoints

Community maintaining fast ports of models (e.g., from Safetensors to GGUF) is critical for rapid experimentation on edge hardware and ICP.

## 🧪 On-Device Experiments
Real-world performance of small GGUF models (3B, 7B):
- GGUF 3B Q4 quantized models can run inference locally in <4GB RAM.  
- High viability for browser, edge, and mobile deployments.  
- New `llama.cpp` updates support LLaMA3 and Mistral with speed optimizations for WebAssembly targets.

---

## 🗓 Upcoming Calls & Topics

| Date     | Topic                                                                                                 | Presenter     |
|----------|-------------------------------------------------------------------------------------------------------|---------------|
| June 05     | World Computer Summit review |        |
| Future | Session on Efficient LLMs and DeepSeek                                                               |               |
| future | Session on instruction limit                                                                          |               |
| Future   | Expert session on Active Inference implementations                                                    | Invite TBD    |
