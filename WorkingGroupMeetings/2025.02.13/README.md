# 2025.02.13 Meeting Summary - DeAI Working Group for the Internet Computer (ICP)

## Short Version
The discussion focused on upgrading Internet Computer (ICP) node hardware from Gen1 to Gen3, emphasizing faster AMD EPYC processors, PCIe 5, and improved memory bandwidth for enhanced AI processing. It covered GPU integration, including AMD Instinct and Nvidia options, and the concept of AI subnets for high-performance tasks. The impact of mixing hardware generations on ICP subnets was considered, along with an RFP announcement for AI agent frameworks. Other topics included historical blockchain data access, chain fusion, and community engagement through events and technical discussions. The call provided a deep technical dive into optimizing ICP’s infrastructure for AI advancements.

### Links shared during the call:
* RFP for ICP AI Agents: https://github.com/dfinity/grant-rfps/issues/62
* https://internetcomputer.org/docs/current/developer-docs/ai/overview
* https://wiki.internetcomputer.org/wiki/Node_Provider_Machine_Hardware_Guide#Gen_1_Node_Machine_requirements
* https://forum.dfinity.org/t/draft-motion-proposal-new-hardware-specification-and-remuneration-for-ic-nodes/14202/14?u=garym
* Gen 1 node example: https://www.supermicro.com/Aplus/system/1U/1023/AS-1023US-TR4.cfm
* Gen 3??? exampe server: https://www.gigabyte.com/Enterprise/Rack-Server/XV23-ZX0-AAJ1-rev-3x#Overview
* https://www.amd.com/en/products/processors/server/epyc/ai.html
* https://www.amd.com/en/solutions/ai.html
* https://resources.nvidia.com/l/en-us-gpu
* https://tenstorrent.com/hardware/wormhole
* https://www.d-matrix.ai/product/
* https://www.esperanto.ai/products/
* https://www.techpowerup.com/gpu-specs/?mobile=No&architecture=Ampere&sort=name
* https://www.techpowerup.com/cpu-specs/
* Sharing someone's X thread where they built a server for CPU inferencing DeepSeek 671B model at FP8. 6-8 tokens per second though: https://threadreaderapp.com/thread/1884244369907278106.html

## Long Version

## 1. Hardware Evolution & Upgrades

**Progression Discussion:** Reviewed the evolution from Gen1 to Gen2 node hardware and explored proposals for Gen3 servers.  
**Key Improvements:** Focus on faster AMD EPYC processors (e.g., EPYC Milan vs. Rome), enhanced memory bandwidth, and support for PCIe 5 (which doubles data transfer speeds).  
**Impact:** Upgraded hardware is expected to boost processing power, improve low-level instruction throughput, and facilitate faster on-chain AI computations.  

## 2. GPU Integration & AI Compute

**Accelerator Cards:** In-depth technical discussion about integrating data center–grade GPUs (e.g., AMD Instinct MI300 series, Nvidia options, and alternatives like TensTorrent and D Matrix).  
**Trade-offs:** Considerations on cost, energy consumption, and performance were discussed, including how GPUs could be integrated progressively into existing nodes.  
**Specialized Subnets:** The idea of forming dedicated “AI subnets” using Gen3 hardware to handle high-performance AI tasks while maintaining consensus integrity.  

## 3. ICP Subnet Architecture

**Subnet Design:** Reiterated that ICP subnets typically consist of 13 servers.  
**Performance Considerations:** Discussed the balance between replication (for consensus safety) and performance, especially if mixing Gen3 and Gen2 hardware could downgrade overall performance.  

## 4. Future Directions & Community Engagement

**RFP Announcement:** An RFP has been published seeking proposals from developers or teams interested in leveraging ICP’s infrastructure for AI agent frameworks.  
**Upcoming Agenda:** Plans to discuss community events (e.g., East Denver) and strategies for increasing team involvement in building AI on ICP in upcoming meetings.  

## 5. Data Integration & Chain Fusion

**Historical Data:** Brief discussion on accessing historical data from various blockchains (e.g., for backtesting AI models) and the potential use of chain fusion approaches with canisters and APIs.  

## 6. Technical Resources & Collaboration

**Shared Resources:** Numerous links were provided for hardware specs, performance comparisons, and additional reading.  
**Community Channels:** Encouraged further technical discussion in dedicated Discord channels to dive deeper into low-level hardware details.  

Overall, the call was a detailed technical deep dive into enhancing the Internet Computer’s hardware to support advanced AI applications, with a clear focus on upgrading server hardware, integrating GPUs, and engaging the community in upcoming projects and events.
