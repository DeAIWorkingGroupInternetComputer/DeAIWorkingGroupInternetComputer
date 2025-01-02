# 2024.01.25 Meeting Summary - DeAI Working Group for the Internet Computer (ICP)

- **Introduction to tract-ic-ai by Jeshli**: A pruned-down version of 'tract', which supports 85% of ONNX functionality, a generic machine learning model, and parameter storage template. Focuses on the compatibility of AI models with ONNX format and the challenges of implementing certain functionalities. [tract-ic-ai](https://github.com/jeshli/tract-ic-ai)
  
- **Optimizing 'tract' for AI Applications**: Details of optimizing the 'tract' library for core neural network applications, focusing on pruning unnecessary functionalities to make it more efficient for specific tasks.
  
- **Large Language Models and ONNX Functionality**: Discusses the difficulties of implementing large language models like GPT-2 in the 'burn' library due to the absence of necessary node functions, leading to a preference for pruning down 'tract' instead.
  
- **Rust Connect py AI to IC**: Introduction of a library for demonstrating downloading GPT-2 from Hugging Face, segmenting it, and running it efficiently. Aims to make AI models more accessible and deployable in decentralized networks. [Rust Connect py AI to IC](https://github.com/jeshli/rust-connect-py-ai-to-ic)
  
- **Front-End Development and Tokenizer Implementation**: Touches on front-end development, particularly implementing a tokenizer and the feasibility of running Rust code in the browser for AI applications.
  
- **Community Collaboration and Sharing of Work**: Moments where participants discuss sharing their work on forums and collaborating on AI projects, reflecting the collaborative nature of the community.
  
- **Interest in Impact of Decentralized AI**: Keen interest in understanding and exploring the impact of decentralized AI, even from those without a deep background in machine learning or AI.
  
- **Potential for GPU Environment Linked to Decentralized Networks**: Discussion on the potential of connecting a GPU cluster to a decentralized network like the Internet Computer (IC) to leverage the advantages of smart contracts and enhance performance.
  
- **Privacy Concerns with Decentralized AI and VetKeys**: Challenges of ensuring privacy in decentralized AI, concerns about the security of VetKeys, and the possibility of memory snapshots extracting keys from malicious nodes.
  
- **GPU Infrastructure and Confidential Computing**: Delves into GPU infrastructure and the concept of confidential computing, which includes secure computation enclaves and encrypted computation. Potential of new features in AMD CPUs and NVIDIA GPUs for secure data processing is discussed.
  
- **Challenges of DDoS Attacks on Decentralized Networks**: Ongoing issues like DDoS attacks on decentralized networks, indicating that there are still challenges to be addressed in ensuring the security and reliability of such systems.
  
- **Data Sharing in Multiplayer Mode**: Highlights the multiplayer mode of decentralized AI, where diverse players can benefit from shared data and native integration with blockchain networks.
  
- **Single Player Mode Advantages**: Discussion on individual users or companies focusing on privacy and the reduction of costs by eliminating middlemen.
  
- **Concerns About Encryption and Data Security**: Acknowledgment of the inherent risks in data sharing, acknowledging that encryption is secure until it's broken.
  
- **Personal AI Solutions on the IC**: Recognition of the IC for enabling personal AI solutions. Individuals can have their own AI models running in canisters they fully control, using virtualized hardware rented from the IC.
  
- **Privacy Continuum and Control Over AI**: Introduction of a privacy continuum, suggesting that different solutions offer varying degrees of privacy.
  
- **Anonymous Deployment of AI Models**: Feature of the IC is the potential for anonymous deployment of AI models, adding a layer of privacy.
  
- **Ongoing Discussion and Follow-Up**: Interest in continuing the discussion on the advantages of AI deployment on the IC with a plan for a follow-up post to gather more ideas.
