# 2025.06.19 Meeting Summary - DeAI Working Group for the Internet Computer (ICP)

## Short Version
The DeAI Working Group is developing a structured model selection framework to identify LLMs best suited for ICP AI use cases and deployment. By categorizing model families and variants by size, architecture, licensing, runtime compatibility, and deployment feasibility, the group aims to match model capabilities—ranging from simple tool use (tiny models) to complex multi-agent planning (large models). Special emphasis is placed on open-source models like OLMoE and Gemma, support for lightweight runtimes like GGUF and vLLM, and the creation of a shared benchmark and spreadsheet tool to guide the community in choosing the right model for decentralized deployment on ICP.

### Links shared during the call:
* AI4AI Infrastructure Options Analysis: https://docs.google.com/spreadsheets/d/1a-NzZeh6D9smxovW7ByYOx7Ls1tRqBJyaS9gXVzRy-Y/edit?usp=sharing
* Recommended AI blog: https://www.interconnects.ai/
* Research on LLM Size vs. Agentic AI Capabilities: https://docs.google.com/document/d/1IbaQqDzyXbLetGtLzuFWdv1u7vl8LKtEDaOissv6Czo/edit?tab=t.0#heading=h.umqucaflsn3i
* https://allenai.org/
* https://forum.dfinity.org/t/introducing-the-llm-canister-deploy-ai-agents-with-a-few-lines-of-code/41424/54?u=patnorris
* https://ai.meta.com/blog/llama-4-multimodal-intelligence/

## Long Version
## Model Family Overview and Spreadsheet Work

A shared spreadsheet is being developed with:
- Top-level model families (e.g., LLaMA, Mistral)
- Variants within each family, including size and specialization.

Suggested structure:
- One table for families.
- One table for individual variants.
- Add columns for license, ownership, and runtime support.

Source inspiration came from the SG Lang site’s model summary.

---

## Model Runtime Compatibility

- Important to map models to runtime engines (e.g., vLLM, HuggingFace Transformers, Modular).
- Possible approach: work backwards from desired models and then identify compatible runtimes.
- **Goal**: identify models and runtimes that can be realistically run on the Internet Computer or via remote inference.

---

## 🔬 Model Families and Architectures
- Discussion on grouping by architecture (e.g., LLaMA and Mistral being closely related).
- Shared architecture = easier deployment and interchangeability across variants.
- Focus on families that have multiple sizes (tiny, small, medium, large).

**Notable Mentioned Families:**
- Minimax (China) – high-performing.
- OLMoE by Allen AI – fully open-source, including training code, datasets, and methodology. Strong transparency.

Interest in families with open weight and training stack access.

---

## 🧪 Model Size Categories for Agentic AI

**Suggested categorization:**
- Tiny: ~1–3B
- Small: ~3–7B
- Medium: ~13B
- Large: ~70–100B
- Huge/Foundation Models: >100B (possibly beyond realistic deployment for ICP)

**Agentic Capability Mapping:**
- Small models can handle reliable single tool use.
- Medium ones can handle multi-step flows.
- Large models required for advanced planning and contextual understanding.

Hardware implications (e.g., RAM/GPU requirements) were discussed in detail, with 70B+ models requiring 32–100+ GB VRAM.

---

## 🔩 Hardware & Quantization Considerations

- With 8-bit quantization (INT8/FP8), ~1 byte per parameter is still the norm.

**Deployment aims to:**
- Run smaller models on CPU (SIMD-capable).
- Run medium and large models on GPU (ideally on a single device).

Foundation model deployment (>120B) is unrealistic for most ICP scenarios due to memory constraints.

---

## ✅ Practical Takeaways

- Model families should ideally support a range of sizes.

**Selection criteria include:**
- Performance
- Runtime compatibility
- Open licensing and documentation
- Practical deployment feasibility

---

## Runtime + Hardware Mapping

- Need to link models with runtime + deployment profiles:
  - vLLM / HuggingFace Transformers: Broad compatibility.
  - Mojo (Modular): Optimized for fast inference.
  - GGUF: Local CPU/GPU quantized inference.

**Highlighted GPU constraints:**
- 70B requires 32–80 GB VRAM (FP16–INT4).
- 7B can run on laptop-class GPUs or even CPUs (INT4/INT8).

Large models require hosting; smaller models could run on client.

🧠 **Plan**: Add deployment target field (e.g., client, edge, server) to each model entry.

---

## Open Source and Reproducibility Focus

**Special interest in:**
- OLMoE by Allen AI: Open training pipeline, data, eval.
- Gemma: Google’s small models with permissive use.

**Potential “DeAI Recommended Models” list based on:**
- Transparency
- Licensing (no use restrictions)
- Runtime accessibility
- Practical ICP deployment

---

## Future Work

**Next steps:**
- Fill in initial spreadsheet fields collaboratively.
- Align agentic use case requirements with model size & runtime options.
- Highlight missing benchmarks (e.g., not all models have evaluated agentic tasks).

**Long-term:**
- Use leaderboard results (e.g. Berkeley's) to empirically validate size–capability thresholds.
- Potentially develop “DeAI agent benchmark” suite.

---

## ✅ Summary Takeaways
- Agentic capability scales with model size, but many agent use cases are feasible with 7B–34B models.
- Runtime compatibility and deployment form (local/off-chain/on-chain) are decisive factors.
- Transparent open-source families will be prioritized.