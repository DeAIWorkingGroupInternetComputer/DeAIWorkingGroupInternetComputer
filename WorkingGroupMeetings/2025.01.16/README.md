# 2025.01.16 Meeting Summary - DeAI Working Group for the Internet Computer (ICP)

## Short Version
The DeAI Working Group call was a joined session with the DFINITY AI team. It focused on integrating AI and GPU capabilities into the Internet Computer Protocol (ICP), deploying small-scale AI applications using CPUs, optimizing matrix multiplication, and exploring future hardware upgrades like AMD Zen 5 CPUs. Collaboration opportunities with networks like Fetch.AI and Swarm were discussed, alongside the potential for decentralized MCP servers for diverse data sources. The group emphasized balancing flexibility and efficiency, promoting community demos, and creating resources to showcase current AI capabilities while advancing toward GPU-based solutions.

### Links shared during the call:
* Llama 3.1 1B: https://xxydu-fqaaa-aaaam-ad2ka-cai.icp0.io/ 

## Long Version
# Purpose and Agenda
- **DFINITY Team Introductions**: Welcomed new members involved in AI-related initiatives within the Internet Computer Protocol (ICP) ecosystem.
- **Focus Areas**:
  - Progress in integrating AI and GPU capabilities into ICP.
  - Updates on AI projects, experiments, and potential collaborations.
  - Identifying challenges and actionable next steps.

# Key Updates and Discussions

## 1. Team Introductions
- Roles included growth managers, AI leads, and developer relations engineers, highlighting diverse expertise and responsibilities within AI.

## 2. GPU Integration
Continued research on a GPU subnet
  - Implement "GPU Workers" using HTTP outcalls to handle workloads.
  - Explore smaller subnets (e.g., 5-node setups) to optimize costs and performance.

## 3. Current AI Experiments
- Deployment of a Llama 3.2 1B parameter model on ICP mainnet for CPU-based inference testing. 

- Test application: https://xxydu-fqaaa-aaaam-ad2ka-cai.icp0.io/, code open-source
- **Performance Results**:
  - Achieved ~1.5 tokens/sec, with optimization potential.
  - Using AVX2 instructions and multi-core CPUs improved inference performance.
- **Optimization Opportunities**:
  - Introduce optimized matrix multiplication as a system API.
  - Utilize additional CPU cores (32–64 available per node) to boost AI workload execution.

## 4. Future Hardware and Protocol Enhancements
- Investigate using AMD Zen 5 CPUs for improved AI task performance.
- Enhance memory management to keep models preloaded in RAM, reducing repetitive loading costs.

## 5. Collaboration Opportunities
- Discussed partnerships with networks like Fetch.AI, Swarm, and NEAR for decentralized AI services.
- Proposed creating decentralized MCP servers to access diverse AI data sources.
- Encouraged community demos and sessions to share progress and gather feedback.

# Next Steps and Action Items

## Experimentation
- Optimize matrix multiplication for AI workloads.
- Conduct performance tests on smaller subnets and CPU-based inference engines.

## Community Engagement
- Host discussions on GPU integration and replication factor adjustments.
- Share open-source tools and benchmarks for community collaboration.

## Educational Initiatives
- Create resources showcasing small LLMs (<1.5 billion parameters).
- Plan sessions to highlight current AI capabilities on ICP, including demos by community members.
