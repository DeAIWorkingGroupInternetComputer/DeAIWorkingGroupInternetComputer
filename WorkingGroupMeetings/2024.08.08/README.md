# 2024.08.08 Meeting Summary - DeAI Working Group for the Internet Computer (ICP)

## Short Version
During today's DeAI Working Group call for the Internet Computer, the primary focus was on discussing hardware options for optimizing AI workloads. The group explored various GPUs and AI accelerator cards, considering factors such as cost, power efficiency, and suitability for both inference and training. The discussion highlighted the potential of Tens Torrent's wormhole cards, which offer a balance of performance and affordability, and emphasized the importance of an open-source software stack for flexibility and problem-solving. There was also mention of ongoing efforts to integrate GPU functionalities into the IC's host functions and the potential need for customized hardware solutions to support AI-driven tasks effectively.

### Links shared during the call:
* https://tenstorrent.com/hardware/wormhole 
* https://www.esperanto.ai/ 
* DeAI manifesto to contribute to: https://docs.google.com/document/d/1GM_QzDhU2DAzWm3C5RzU861qEje2lzy7Un_l_dYdhvc/edit#heading=h.8jg466jkf1fh 
* DeVinci alpha release: https://x6occ-biaaa-aaaai-acqzq-cai.icp0.io/ 

## Long Version
## Key Topics Discussed:

### Introduction and Updates:
- Brief opening remarks and updates on the hardware research side were provided.
- Emphasis on finding a feasible, cost-effective, and energy-efficient way forward in terms of engineering.

### Hardware Options for AI:
- Discussion about the limitations and costs of current GPUs (NVIDIA, AMD).
- Mention of alternative hardware like FPGA-based devices and the need for a balance between cost and functionality.
- Highlighted that purely inference-only hardware might be too restrictive.

### Potential Solutions:
- Introduced Tens Torrent as a viable hardware option due to its balance of training and inference capabilities, power efficiency, and lower cost (~$2000 compared to $20,000 for high-end GPUs).
- Discussion on the flexibility and open-source nature of the Tens Torrent software stack.

### Implementation and Testing:
- Plans to order Tens Torrent wormhole cards and test them in a Gen. 2 node.
- Aim to make the setup available to developers for experimentation.
- Potential for using existing spare nodes to reduce costs and expedite testing.

### Software Stack and API:
- Emphasis on the importance of a generic and open software stack for integration with IC replica nodes.
- Discussion on the WASM host function call out method and the need for deterministic processing.

### Future Plans:
- Consideration of scaling out the compute capacity using high-speed Ethernet connections between cards.
- Exploring the possibility of different subnets for inference and training, but leaning towards a general-purpose solution that can handle both.

### Dfinity’s Role:
- Dfinity is looking to hire someone with GPU expertise to help build out the host functions.
- Current efforts to add bindings for Web GPU for local development and proof-of-concept work.

### Challenges and Considerations:
- Importance of deterministic processing in GPUs for replicating node functionality.
- The necessity of transparency and open-source access to diagnose and solve potential problems.

## Action Items:
- Order and install Tens Torrent wormhole cards in Gen. 2 nodes.
- Share the setup with developers for initial testing.
- Continue exploring and validating the Tens Torrent platform for potential wider adoption in the IC infrastructure.


