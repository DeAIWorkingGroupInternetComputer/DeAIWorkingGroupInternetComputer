# 2025.04.17 Meeting Summary - DeAI Working Group for the Internet Computer (ICP)

## Short Version
Today's DeAI Working Group call focused on TensTorrent's new Black Hole ASIC cards, which offer significant performance upgrades from their previous generation by moving from 12nm to 6nm lithography, using cost-effective GDDR6 memory instead of NVIDIA's HBM. The group discussed practical implications of model sizes and agreed on the need for standardized open-source models suitable for agentic workflows on the Internet Computer. Malith shared insights on performance bottlenecks in multi-GPU setups and highlighted advantages of NVIDIA's advanced memory interfaces like NVLink. Lastly, the group acknowledged the necessity of evaluating emerging inference software such as Modular’s inference server as potential improvements over existing solutions.

### Links shared during the call:
* Tenstorrent hardware update (Blackhole cards): https://openfuture.tenstorrent.com/
* https://tenstorrent.com/hardware/blackhole
* https://github.com/tenstorrent/tt-forge/blob/main/README.md
* https://github.com/tenstorrent/tt-inference-server/blob/main/README.md
* https://github.com/orgs/tenstorrent/projects/17/views/5
* https://www.youtube.com/watch?v=S3n_9gX-9lw&t=2400s
* https://www.nvidia.com/en-us/products/workstations/dgx-spark/
* https://www.nvidia.com/en-us/data-center/h100/?ncid=no-ncid
* https://www.nvidia.com/en-us/data-center/h200/?ncid=no-ncid
* https://www.modular.com/blog/max-25-2-unleash-the-power-of-your-h200s-without-cuda
* https://forum.dfinity.org/t/new-node-specification-my-bucket-list-option-2/43468

## Long Version
Today's DeAI Working Group call focused primarily on the new developments from TensTorrent, highlighting their latest Black Hole ASIC cards designed specifically for AI workloads. Icarus walked the group through their recent tech updates. TensTorrent has revamped their website and software stack, providing open-source software optimized for their unique network-on-chip architecture, which uses Ethernet for low-level chip-to-chip communication.

The Black Hole cards represent TensTorrent's move towards a production-ready solution, significantly upgrading from their previous generation Wormhole cards by shifting from a 12nm to a more efficient 6nm lithography. This has effectively doubled their performance, making these cards a more viable competitor against NVIDIA's offerings, though still less energy-efficient due to differences in lithography scale.

Notably, TensTorrent cards utilize cheaper GDDR6 memory instead of NVIDIA's high-bandwidth HBM, achieving cost-effectiveness with a slight trade-off in operational efficiency. Their current developer cards are competitively priced (around $1,400 USD per card), offering a substantial reduction in capital costs compared to NVIDIA’s high-end GPUs.

The group discussed the practical considerations of model sizes and performance, especially around open-source models suitable for agentic workflows on the Internet Computer. There was agreement on the necessity to define a standardized set of open-source models that provide sufficient performance for the group's intended applications.

Malith contributed valuable insights based on their direct experience, particularly highlighting that multi-GPU setups often do not linearly increase performance due to interconnect and memory bandwidth bottlenecks. Malith also shared real-world insights about using NVIDIA’s H100 and upcoming B200 Blackwell GPUs, noting substantial performance benefits from advanced memory interfaces like NVLink.

The call also explored considerations for inference software stacks, with mentions of frameworks such as VLLM, which, despite ease of use, encounter significant performance dips with larger prompts. The conversation concluded with recognition of the need to evaluate emerging software solutions like Modular's inference server, which might offer promising alternatives to existing platforms.

---

## 🗓 Upcoming Calls & Topics

| Date     | Topic                                                                                                 | Presenter     |
|----------|-------------------------------------------------------------------------------------------------------|---------------|
| Apr 17   | AI4AI – Accelerated AI Infrastructure for ICP                                                                | Icarus        |
| Apr 24   | IConfucius – Fully On-Chain AI Agent on ICP                                                           | icpp (onicai) |
| May      | ANIMA demo ([link](https://forum.dfinity.org/t/introducing-the-llm-canister-deploy-ai-agents-with-a-few-lines-of-code/41424/35?u=patnorris)) | swift         |
| May (tbd)| Session on Efficient LLMs and DeepSeek                                                               |               |
| May (tbd)| Session on instruction limit                                                                          |               |
| Future   | Expert session on Active Inference implementations                                                    | Invite TBD    |
