# 2025.07.17 Meeting Summary - DeAI Working Group for the Internet Computer (ICP)

## Short Version
Today's DeAI Working Group call explored the rapidly evolving landscape of decentralized AI infrastructure, highlighting breakthroughs in open-source LLMs (like Kimi K2 and Phi-3), 4-bit quantization methods (HIGGS), and efficient inference hardware such as NVIDIA’s Blackwell GPUs and analog accelerators from Axelera and EnCharge. vLLM emerged as the dominant model-serving framework, with growing support for multi-modal and CPU-only inference. The group discussed how community members could self-host inference runners and contribute to a decentralized registry of model runtimes, as the DeAI ecosystem moves toward fast, modular, and self-sovereign AI execution.

### Links shared during the call:
* https://vram.ai/
* https://www.youtube.com/watch?v=IST4ME7nfZk&feature=youtu.be
* https://github.com/Sid31/team-ai/tree/main
* https://moonshotai.github.io/Kimi-K2/
* https://huggingface.co/docs/transformers/v4.48.0/en/quantization/higgs
* https://www.marktechpost.com/2025/04/11/llms-no-longer-require-powerful-servers-researchers-from-mit-kaust-ista-and-yandex-introduce-a-new-ai-approach-to-rapidly-compress-large-language-models-without-a-significant-loss-of-quality/
* https://axelera.ai/
* https://www.enchargeai.com/
* https://en100.enchargeai.com/
* https://docs.google.com/spreadsheets/d/1a-NzZeh6D9smxovW7ByYOx7Ls1tRqBJyaS9gXVzRy-Y/edit?gid=712966265#gid=712966265

## Long Version

**Focus:** AI Model Trends, Open Source Runtimes, Quantization, Hardware Advances, Software Stack Maturity, and Community Infrastructure Strategy

---

## 1. Introductions

**VRAM.ai** introduced by its CEO:
- Focus: Secure AI–blockchain use cases (e.g. encrypted inference for hospitals, banks).
- Goal: Enable innovation on private data using cryptographic techniques (e.g. via ICP).

**Qryptiq** expressed interest in demoing work in a future session (July 31).

## 2. Reflections & Context

Emphasis on aligning DeAI infrastructure plans with rapid developments in:
- Open models  
- Hardware acceleration  
- Inference software stacks

## 3. Model Developments

📌 **Kimi K2 (China)**:
- Fully open-source LLM including training stack.
- Claims competitive benchmarks vs. OpenAI/Anthropic/Google.
- Smaller in parameters than DeepSeek but similarly performant.
- Inference-ready via VLLM and SGLang.

📌 **Microsoft's Phi-3 Mini Flash**:
- Released with long context window and reasoning capability.

📌 **NVIDIA Open Audio Model**:
- Mixture-of-Experts model for audio-to-text, text-to-audio, and audio reasoning.
- Fully open-source including training dataset.

## 4. Quantization Advances

📌 **HIGGS (Yandex et al.)**:
- A new linear quantization method down to 4-bit without using training data.
- Matches FP16 performance with 2x inference speed.
- Compatible with Hugging Face Transformers.

**Tip**: Framework called **UNSLOTH** supports fine-tuning already quantized models.

## 5. Hardware Acceleration

Focus on capital-efficient inference hardware:

**NVIDIA RTX Blackwell Workstation GPU (B200, GDDR7, 96 GB RAM):**
- ~$8K with support for large 4-bit quantized models (160–180B params).
- Standalone, no NVLink, efficient for single-node inference workloads.
- Well-suited for running inference on ICP-based AI workers.

**New energy-efficient accelerators:**
- **Axelera AI**:
  - Analog in-memory compute; PCIe accelerator delivers 200 TOPS at <60W.
  - Targets vision and edge, but also supports small LLMs (8B).
- **EnCharge AI**:
  - Analog in-memory architecture, similar power/performance profile.

❌ **Esperanto (RISC-V based):** shut down this week, showing risk in niche silicon ventures.

## 6. Serving Framework Maturity & Trends

**vLLM** has become the go-to serving backend for most state-of-the-art models:
- Support for PagedAttention, high throughput, and long context.
- Now supports multi-node inference.
- Rapid adoption across:
  - DeepSeek, Kimi, Baichuan, Qwen, Meta, Mistral, and more.

**Other popular serving runtimes:**
- TGI (Transformers Generation Inference)
- MLX (Apple)
- SGLang (LlamaIndex + LangChain integration)
- LMDeploy (from InternLM team)

> 🔁 **Trend**: Each major foundation model release is now paired with its own optimized inference stack.

## 7. Multi-Modal Inference

Growing adoption of unified inference runtimes for multi-modal models (e.g., LLaVA, CLIP, OpenVoice).

**Examples:**
- LLaVA integrates smoothly with VLLM.
- OpenVoice is gaining traction as a low-latency speech model.

## 8. FastCPU Inference

**Example:** TinyLlama + GGUF + llama.cpp can now reach:
- 50+ tokens/sec on a regular laptop CPU, even with long context windows.

Quantization + CPU-only inference now viable for agents and offline applications.

## 9. Long Context and Smart Routing

**Context lengths now reaching:**
- 1M tokens with FlashAttention 2 (experimental)
- Realistic production: 128K–256K for vLLM and Mistral-style models.

**Smart routing and caching mechanisms** (e.g. vLLM's tokenizer cache) reduce latency and cost.

## 10. Software & Backend Stack Considerations

The DeAI Working Group is tracking maturity of:
- Model format standards (GGUF, Safetensors, etc.)
- On-device runners (e.g. llama.cpp, MLC)
- Cloud inference runtimes (VLLM, TGI)
- GPU inference containers (NGC, OCI-compliant)

**Potential future component:**
- ICP-native inference as WebAssembly containers or with backend-proxied GPU inference

## 11. Community Infrastructure: Direction & Vision

**Idea:** Let DeAI community provision and maintain own inference runners.
- E.g., Fun compute nodes opt in to support specific model runtimes.

**Options for DeAI Registry:**
- Declarative metadata standard (e.g. like model-cards)
- Reward distribution for successful task completions

## Key Takeaway

The DeAI stack is converging around flexible, fast, and quantized model runtimes (like vLLM and llama.cpp), with increasing specialization for modalities and hardware constraints. The community is exploring ways to maintain interoperability while enabling decentralized, self-sovereign inference infrastructure.