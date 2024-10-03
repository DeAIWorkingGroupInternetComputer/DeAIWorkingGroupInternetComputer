# 2024.10.03 Meeting Summary - DeAI Working Group for the Internet Computer (ICP)

## Short Version
In today's DeAI Working Group call, participants discussed the challenges of implementing shared stable storage for canisters to avoid re-uploading large AI models across subnets. The conversation also focused on the serialization of tensors, exploring the need for standardized formats such as ONNX or MLIR for data sharing between canisters. The group also touched on the future potential of using GPU subnets for AI computation, dealing with issues like determinism and instruction limits, and the possibility of creating decentralized systems to rent out and protect training data for AI models.

### Links shared during the call:
* https://onnx.ai/onnx/api/serialization.html
* https://mlir.llvm.org/docs/BytecodeFormat/
* https://mlir.llvm.org/docs/Dialects/TOSA/
* GPU comparison: https://x.com/Yuchenj_UW/status/1835532542172430700
* GPU benchmark: https://www.tomshardware.com/reviews/gpu-hierarchy,4388.html

## Long Version
Today's DeAI Working Group call for the Internet Computer focused on two main topics: shared storage across canisters and advances in tensor serialization.

The discussion around shared storage for canisters highlighted a desire to create a read-only stable storage object that can be shared between canisters on the same subnet, thus preventing the need to re-upload large models and data, enhancing efficiency. However, this idea faced challenges due to current siloed security mechanisms, and further exploration is required.

The conversation shifted to tensor serialization, where progress was shared on serializing tensors into blobs, including multiple data types. Participants discussed the need for a standardized format for tensors, aligning with past suggestions to define standards across various aspects like large language model APIs and vector databases. There was also a deep dive into serialization formats like ONNX, MLIR, and CBOR, with participants considering their pros and cons in supporting tensor data and message passing.

Additionally, the call touched on non-determinism in GPUs, where a participant shared findings from tests on Nvidia A100 GPUs, showing no significant evidence of non-determinism. The group debated the implications of this on future development and the need for further testing.
Lastly, the group briefly discussed infrastructure security concerns, particularly around handling sensitive data during AI model training, with a focus on decentralized security guarantees to prevent data theft and ensure privacy.

Overall, the meeting continued to refine the group's technical goals, with an emphasis on balancing security, efficiency, and standards for AI and decentralized systems on the Internet Computer.

