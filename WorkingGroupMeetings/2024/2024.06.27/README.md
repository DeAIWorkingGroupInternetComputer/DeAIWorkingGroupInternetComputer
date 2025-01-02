# 2024.06.27 Meeting Summary - DeAI Working Group for the Internet Computer (ICP)

## Short Version
In the DeAI Working Group's call for the Internet Computer, key points included highlighting AI product success stories via a shared survey to strategize marketing and measure metrics for partnerships, aiming to position ICP prominently in the AI space with data partners like CoinMarketCap. Kiko presented his integration of the Flashlight library into ICP, sharing his experiences and challenges in bringing C++ projects, such as a soccer simulator and a physics engine, to the platform, and demonstrated training a neural network on-chain. The discussion covered the use of SIMD instructions to enhance GPT-2 transformer performance, resulting in a 1,230% efficiency increase, and Jeshli’s plan to publish related code and tokenizers. Efforts to bring the LLaMA model to ICP were detailed by Giles, showcasing modular implementation in Rust and the feasibility of running computations on-chain despite latency issues. Community support, funding for computational tasks, and future directions focused on code optimization and deploying the first open-source LLaMA model on-chain were also discussed.

## Long Version
The DeAI Working Group for the Internet Computer held a call focusing on the following key points:

### Highlighting Success Stories:
- The group aims to highlight AI product success stories on the Internet Computer Protocol (ICP).
- A survey was shared in the decentralized AI channel on Discord for teams to fill out, helping to strategize marketing efforts and highlight their achievements.

### Partnerships and Metrics:
- The survey data will inform partnerships and showcase the metrics teams use to measure their success.
- Partnerships with data partners like CoinMarketCap aim to position ICP as a significant player in the AI space.

### Project Presentation by Kiko:
- Kiko presented his work on integrating the Flashlight library into ICP.
- He shared his experience of bringing C++ projects, including a soccer simulator and a physics engine, to ICP.
- Kiko demonstrated how deep learning and AI can be integrated into the game, enabling the training of soccer players using machine learning algorithms.

### Challenges and Solutions:
- Kiko discussed the challenges faced in porting C++ code to ICP, such as unsupported features and the need to remove GPU code for compatibility.
- He detailed the process of using Flashlight, a C++ library with a smaller footprint than TensorFlow, to implement deep learning on ICP.

### Technical Demonstration:
- A live demonstration showed the training of a neural network running on-chain using Flashlight.
- The importance of having a small code footprint for blockchain deployment was emphasized.

### Community Support and Future Directions:
- Kiko acknowledged the support from the community and tools like icpp_pro in overcoming development hurdles.
- Suggestions were made to explore using WASI2IC project for better compatibility and handling of standard C library features.

### SIMD:
- The improvements of SIMD instructions to enhance the performance of the GPT-2 transformer were discussed.
- The demo illustrated a 1,230% increase in efficiency using SIMD instructions for the GPT-2 computations.

### Code and Tokenizer Integration:
- The code and tokenizers for GPT-2 were discussed, with plans to publish the code for others to benefit from.
- Jeshli shared the public repository, containing examples and scripts for downloading and converting models to ONNX format.

### Bringing LLaMA to ICP:
- A detailed presentation on the efforts to bring the LLaMA model (a large language model) to the Internet Computer Protocol (ICP).
- The project, named "YLLaMA," focuses on creating a modular implementation of LLaMA in Rust.
- The goal is to perform inference on an existing open-source large language model and eventually enable on-chain training.

### Technical Demonstration by Giles:
- A technical demo was presented, showing how a simple canister can perform matrix-vector multiplication, a critical operation for LLaMA inference.
- The demo proved the feasibility of running such computations on ICP, although with significant latency.

### Challenges and Solutions:
- The challenges of integrating large models like LLaMA on ICP were discussed, including the need for significant computational resources and managing dependencies.
- The solution involves quantization and breaking down computations across multiple canisters to handle large models efficiently.

### Community Support and Funding:
- The presenter sought support for acquiring cycles to run the computationally intensive tasks on ICP.
- The team mentioned available developer grants and coupons to help with the required cycles.
Future Directions:
- The focus will be on tidying up the code, further optimizing the canisters, and deploying the model on the Internet Computer.
- The goal is to showcase the first real open-source LLaMA model on-chain, despite the inherent latency challenges.



