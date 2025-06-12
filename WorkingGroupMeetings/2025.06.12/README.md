# 2025.06.12 Meeting Summary - DeAI Working Group for the Internet Computer (ICP)

## Short Version
In today’s DeAI Working Group call, the main focus was on Tiago’s demo, which showcased Vibe Coding with VS Code and a template he and Antione created to support live feature implementation, test generation, and AI pair programming. The tool, already used in hackathons, impressed the group with its potential for speeding up development. It could in the future also integrate with the MCP server to support agent workflows on ICP. Beyond the demo, the group discussed ICP’s strategic strengths for AI development and Caffeine AI, debated fine-tuning versus RAG approaches, explored WASM-level optimizations, and aligned on three priority tracks: infrastructure enhancements, knowledge sharing, and cross-platform AI interoperability.

### Links shared during the call:
* VIBATHON: https://lu.ma/97xb87xv?tk=0IBAVA
* https://github.com/pt-icp-hub/IC-Vibe-Coding-Template
* https://www.youtube.com/watch?v=ZuNUy13wmlI&t=5753s
* https://datapond.ai/
* https://open.substack.com/pub/codinginterviewsmadesimple/p/fine-tuning-llms-is-a-huge-waste

## Long Version
## DeAI Working Group – Call Summary

### 1. Caffeine AI Observations
The group noted the rise in shared demos from the community.  
Curiosity remains about Caffeine AI’s underlying architecture: it likely uses a combination of fine-tuned models (Motoko for backend, possibly via OpenAI; JavaScript frontend via Anthropic or similar).  
Will be interesting to see if system is modular and may allow user-selectable models in future.

### 2. Cost & Business Model Concerns
Discussion around the long-term sustainability of services using off-chain AI.  
Participants agreed that without a viable monetization model, scaling to millions of users would become economically infeasible.

### 3. ICP’s Strategic Advantage
Caffeine AI seen as a good Web2-to-Web3 onboarding path.  
Strong emphasis on ICP’s ease of deployment and developer experience (especially in DevOps).  
Highlighted importance of showcasing ICP features like Chain Fusion and vetKD to developers and non-devs alike.

### 4. Fine-Tuning vs. RAG Debate
Participants reviewed a critical article on the risks of overusing fine-tuning (e.g., risk of overwriting pretrained knowledge).  
For most cases, retrieval-augmented generation (RAG) combined with prompt engineering and large context windows is preferred.  
Fine-tuning is deemed useful in niche contexts, such as writing Motoko code.

### 5. Infrastructure & Goals Discussion
Three main “tracks” were proposed for the working group:
- **Enhancing AI Capabilities on ICP** (e.g. instruction limits, efficient execution)  
- **Knowledge Exchange & Demos** (e.g. project feedback, shared learnings)  
- **Broader AI Compatibility** (e.g. AI chain fusion, protocols for cross-platform AI interaction)

### 6. Hardware & Software Stack Coordination
Group discussed separating software model selection from hardware optimization.  
VLLM highlighted as a strong inference stack, including recent Red Hat developments.  
Group spreadsheet continues to document model/hardware compatibility.

### 7. WASM & Instruction Optimization
Follow-up on Jeshli’s proposal to explore improving performance via instruction-level changes in WASM.  
Group supports scheduling dedicated sessions to investigate this further.  
Potential performance gains identified through tighter CPU-level optimization.

### 8. Tiago’s Demo: Vibe Coding
Tiago and Antoine presented a coding template used in hackathons to boost developer productivity using AI pair programming.  
Introduced Claude-driven coding assistant in VS Code with Copilot.

**Highlights included:**
- AI-assisted feature implementation (live coding)  
- Emphasis on unit testing for AI-generated code  
- Future enhancements could include MCP server integration for agent workflows  

**Features:**
- Feature suggestions  
- Live coding assistant  
- Tests written and validated by AI  

**Plans:**
- Integrate with MCP server for AI workflows  
- Possibly offer open template to other developers  
- Organize an upcoming vibe coding hackathon for IPC: https://lu.ma/97xb87xv?tk=0IBAVA
