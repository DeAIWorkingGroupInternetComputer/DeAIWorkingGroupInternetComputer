# 2025.01.30 Meeting Summary - DeAI Working Group for the Internet Computer (ICP)

## Short Version
The onicai team presented their work on self-sovereign AI using ICP, focusing on deploying the Deep Seek AI model on-chain and optimizing its performance. Key challenges include high computational costs, instruction limits, and memory inefficiencies. Proposed solutions involve optimizing llama.cpp, introducing AI Workers with GPUs for scalable AI execution, and exploring TEEs for secure verification. Additionally, a C++ Canister Development Kit bootcamp aims to attract more developers. Dfinity is actively researching AI optimizations, and community feedback is sought to determine the best path forward for decentralized AI on ICP.

### Links shared during the call:
* C++ bootcamp for ICP: https://www.onicai.com/#/icpp-pro
* LLMs in canister: https://github.com/onicai/llama_cpp_canister
* Ported framework: https://github.com/ggerganov/llama.cpp
* Proof-of-AI-Work: https://www.onicai.com/#/poaiw
* https://solarpunk.buzz/decentralized-multimedia-libraries-launched/
* 1bit LLMs: https://arxiv.org/abs/2402.17764 

## Long Version
# Introductions and Overview

New participants were introduced, including Angelo, a Dfinity employee responsible for support operations, deny lists, and boundary nodes.  
The onicai team (including Arjaan and Patrick) presented their work on self-sovereign AI using ICP as the platform of choice.  

## 2. Onicai’s Recent Work  

- They discussed their Deep Seek On-Chain AI Model and the Proof of AI Work protocol.  
- The goal is to gather feedback, explore collaborations, and drive discussions around decentralized AI.  

## 3. C++ Bootcamp Initiative  

- Arjaan announced a C++ Canister Development Kit bootcamp to attract more developers to ICP.  
- Abhishek, the technical writer hired, has produced video tutorials and documentation.  
- This was so far funded through the icpp-art NFT sale. Additional funding is needed to complete the whole bootcamp materials.  

## 4. Deep Seek AI Canister Deployment  

### Experimentation with running Deep Seek AI models in ICP canisters  

#### **llama_cpp_canister Upgrade:**  
- Upgraded to the latest llama.cpp to support Deep Seek models  
- Took 1.5 weeks to complete  

#### **Testing Results:**  
- Successfully deployed a 1.5 billion parameter model  
- Generates two tokens per update call before hitting the instruction limit  
- Achieved over 111,000 views on a post about the experiment  
- Memory is not a bottleneck, but instruction limits are a major constraint  

## 5. AI Optimization and Cost Analysis  

- The Deep Seek model is **5x more expensive** than the Qwen 0.5B parameter model on ICP due to its verbosity and computation cost.  

### **Key bottlenecks:**  
- Instruction limit per call  
- Inefficient memory management (model reloads from disk every update)  
- Matrix multiplication performance bottlenecks  

## 6. Proposed Solutions for AI on ICP  

### **1️⃣ Optimizing the Existing Model**  
- Improving llama.cpp performance through memory caching and instruction optimizations.  

### **2️⃣ AI Workers Concept**  
- AI Workers would be dedicated nodes with GPUs, running AI models externally but verifying responses through ICP.  
- Would allow running larger models (e.g., 8B and 70B parameter models) efficiently.  
- Would maintain Byzantine Fault Tolerance (BFT) to ensure correctness.  

### **3️⃣ Using TEEs (Trusted Execution Environments)**  
- Alternative approach using TEE-based AI agents with ZK proofs for verification.  
- TEEs are very expensive ($40,000 per GPU instance) and could limit adoption.  

## 7. Future Roadmap & Open Questions  

- How can Dfinity prioritize AI optimizations like higher instruction limits or GPU-based AI Workers?  
- Is the AI Workers model more scalable than running AI directly on canisters?  
- Would the community prefer a fully decentralized model or a hybrid approach?  

## Conclusion  

- The AI Workers approach is gaining traction as a viable solution for on-chain AI execution.  
- The Deep Seek model demonstrated feasibility, but optimizations are needed to make on-chain AI practical.  
- Dfinity is actively researching solutions and looking for community feedback on the best path forward.  
