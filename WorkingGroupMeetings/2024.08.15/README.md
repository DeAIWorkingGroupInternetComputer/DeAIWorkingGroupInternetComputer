# 2024.08.15 Meeting Summary - DeAI Working Group for the Internet Computer (ICP)

## Short Version
During the DeAI Working Group call, a presentation was given on Clanopedia, a decentralized, verifiable data source built during the Web3 AI hackathon, focusing on creating a collective knowledge base using a vector database architecture stored on the Internet Computer Protocol. The discussion then shifted to documentation updates, with an extension of the deadline for contributions, and the team explored ongoing work on AI transformers for specific use cases, emphasizing the importance of community collaboration. The call also featured an in-depth discussion on AI regulation, particularly the European Union's AI Act, its implications for high-risk AI applications, and the evolving landscape of global AI governance. The session wrapped up with reflections on the need for future workshops, code walkthroughs, and regular updates on AI regulations, highlighting the importance of staying informed on legal developments as AI technology advances.

### Links shared during the call:
* DeAI docs to contribute to: https://docs.google.com/document/d/1tf6kbzE2Vqxb5I6JUWZzJJpQ0qmGXkOfNqcU4yBWOSQ/edit?usp=sharing 
* DeAI manifesto to contribute to: https://docs.google.com/document/d/1GM_QzDhU2DAzWm3C5RzU861qEje2lzy7Un_l_dYdhvc/edit#heading=h.8jg466jkf1fh 
* DeAI repo for project additions (as PR) and existing projects (incl. Vector dbs): https://github.com/DeAIWorkingGroupInternetComputer/DeAIWorkingGroupInternetComputer/tree/main/Projects
* Vector db by Kinic DAO: https://github.com/ClankPan/ic-vectune/tree/develop/kinic_db_instance

## Long Version
## Clanopedia Demo

During the DeAI Working Group call, a detailed presentation was given on Clanopedia, a decentralized, verifiable, and tamper-proof data source built during the Web3 AI hackathon on Encode. The project aims to create a collective knowledge base managed and used by a community, with a decentralized approach to data creation and usage. Inspired by Vectra, the project utilizes a vector database architecture but stores data on the Internet Computer Protocol (ICP) instead of a local disk, leveraging stable memory within canisters. The presenter demonstrated the functionality using a medical record database, showcasing how the system ranks query results based on cosine similarity of embeddings stored on the blockchain. Future developments include migrating the indexing and operations fully on-chain using Rust canisters to enhance performance and scalability. The presentation concluded with a discussion on voting mechanisms for adding new data, inspired by ERC-20 proposals, and addressing the impact of compute costs on the system. The call highlighted the project's potential and the challenges ahead as it moves towards production.

## DeAI Documentation

In this portion of the call, the focus shifted to documentation updates and volunteer contributions. Jessie initiated the discussion, asking if anyone had progress updates on the documentation tasks they had taken ownership of, and encouraged others on the call to volunteer for remaining tasks. The team acknowledged that while the original time frame for completing the documentation was two months, more time would likely be needed, and the deadline might be extended until October 18th. A Google Doc with a task list was shared for members to sign up for contributions.

## Work on Transformers on ICP

Later in the conversation, a participant inquired about ongoing work related to AI transformers for specific use cases, particularly those running on canisters. The team discussed their exploration into building AI tooling, with a focus on inference as the first use case. The discussion touched on possible approaches and standards, including WASI neural networks and web neural network APIs, and the intention to share research findings with the community for feedback. The segment concluded with a commitment to make the process collaborative and open-source, allowing for community contributions and learning opportunities.

## AI Regulation

In this portion of the call, the discussion transitioned into a conversation about AI regulation and governance, with a focus on the implications of the European Union's AI Act. Participants highlighted how AI systems, especially those used in high-risk areas like healthcare and legal sectors, will be increasingly regulated. The conversation also covered the challenges of defining AI in law, the categorization of AI by risk level, and the possible future of AI regulation, including its impact on both large tech companies and open-source models.

Tim presented an overview of various international AI regulations and their development. He emphasized that AI law is still in its early stages, drawing parallels to the regulatory approaches seen in fields like genetic engineering and nuclear proliferation. The discussion suggested that as AI continues to advance, it will likely face similar global regulatory frameworks.

The conversation also touched on the role of AI in government and military sectors, noting that public sector regulations are already incorporating AI considerations, particularly in national security contexts. The participants concluded by reflecting on how AI's potential for both enhancement and harm may drive future international cooperation and regulation.

## Future Topics

The participants concluded their discussions and reflected on the session. The moderator asked if there were any additional questions, comments, or suggestions for future agenda items. One participant suggested including updates on research outcomes and experiments, particularly around AI model training and deployment in canisters. Others agreed and proposed having more workshops, code walkthroughs, and regular updates on AI regulation and law.

The group discussed the potential of having regular sessions focused on legal and regulatory developments in AI, possibly as a quarterly update. The moderator agreed and noted these suggestions for future calls. The session concluded with thanks to the presenters and an invitation to next week's call.

