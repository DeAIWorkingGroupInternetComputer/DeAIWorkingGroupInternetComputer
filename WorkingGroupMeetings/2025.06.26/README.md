# 2025.06.26 Meeting Summary - DeAI Working Group for the Internet Computer (ICP)

## Short Version
Samuel demoed a powerful new plugin for the Eliza AI agent framework that enables interaction with the Internet Computer (ICP), including wallet management, token swaps, and full NNS neuron control. The modular plugin architecture separates actions, providers, and evaluators, and integrates smoothly via Eliza's character files. With built-in safety features like two-step confirmations, the plugin sets the stage for future capabilities like SNS proposal analytics and autonomous investment insights. Community feedback highlighted it as a major step toward seamless agentic UX on ICP.

### Links shared during the call:
* https://github.com/sam-thetutor/plugin-icp
* https://www.elizaos.ai/faq
* https://www.elizaos.ai/
* https://medium.com/ai-dev-tips/create-ai-agents-with-ai16z-in-15-minutes-639751e6ea69
* https://arxiv.org/pdf/2501.06781
* https://github.com/elizaOS/eliza/issues/844
* https://www.youtube.com/watch?v=UAQMM95TDOY

## Long Version
## 🌐 Opening Discussion

The call opened with a brief discussion about advanced neuroprosthetics and haptic feedback in virtual environments, touching on the long-term implications for a physically interactive metaverse and XR.

## 🤖 Demo: Eliza AI Agent Plugin for ICP

**Presented by Samuel**

Samuel showcased a plugin he developed for Eliza, an AI agent framework designed to operate across multiple platforms (Twitter, Discord, Telegram, Slack). The plugin adds capabilities to interact with the Internet Computer (ICP) blockchain.

### 🔧 Key Features of the Plugin:

#### ICP Wallet Management:
- Check wallet balance  
- Send tokens  
- Swap tokens (e.g., CHAT ↔ ICP)

#### NNS Integration:
- Create and manage neurons  
- Increase dissolve delay  
- Trigger staking actions  
- Retrieve neuron lists

### 🧪 Demo Highlights:
- Real-time interaction with the plugin via a chatbot interface running locally  
- Demonstrated secure use of `.env` variables for ICP wallet credentials  
- Plugin actions and providers were implemented in a modular fashion:
  - **Actions**: Execute commands like send ICP, swap tokens  
  - **Providers**: Manage secure connection and authentication  
  - **Evaluators** (planned): Parse and analyze response data from ICP

### 🧩 Architecture & Configuration:
- Uses a **character file** to define agent personality, skills, model config, and plugin integration  
- Plugins written in JS/TS with specific logic for wallet interaction, NNS operations, and ICP API access  
- Uses message context threading to track multi-step interactions (e.g., confirm before sending tokens)

### 🛡️ Safety Considerations

Samuel explained how hallucinations are mitigated:
- Prompts are structured with transfer templates  
- Two-step confirmation is built-in for sensitive actions like transfers

### 🔮 Future Plans
- Expand support to SNS projects (e.g., OpenChat)  
- Add analytics and insight-generation for SNS governance proposals  
- Enable passive monitoring of SNS performance and investment opportunities

### 💬 Community Feedback

Call participants praised the demo as a “huge step” in agentic UX simplification on ICP.

Suggestions included:
- Adding autonomous SNS analytics (summaries, investment insights)  
- Extending skill definitions and SNS-specific tracking features