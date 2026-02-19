# Terminologies
#### openai library
#### openai agent sdk
#### agent, tools, trace, handsoff, guardrails
#### Deep research - WebSearch, FileSearch, ComputerTool
#### CrewAI
##### CrewAI Crews
##### CrewAI Flows
<img width="468" height="403" alt="image" src="https://github.com/user-attachments/assets/7b50fda3-d763-4499-a35f-fe2f75e2c0ba" />

<img width="703" height="646" alt="image" src="https://github.com/user-attachments/assets/8afce076-1c54-47d2-940f-2a987f6ca524" />

##### GuardRails in CrewAI

#### LangChain
- LangChain is an open‑source framework designed to help developers build applications powered by large language models (LLMs) such as GPT, Claude, Gemini, and others. It provides modular building blocks—like prompts, chains, agents, memory, and data connectors—that make it easier to turn raw LLM capabilities into real, production‑ready AI applications.
- where you're solving problems that involve a lot of interconnected processes, like an agentic platform.
So it's an abstraction layer that allows you to organize your thinking around a workflow of different
activities that could have feedback loops.
It could have times when humans need to get involved.
It could have moments when you need to keep memory, and it allows you to organize all of that in a
very repeatable and easily monitored and stable and scalable way.
- you use this to design agent driven user experiences featuring things like human in the loop, multi-agent collaboration, conversation, history, memory, and what they call time travel, which is all about being able to checkpoint where you are in the process of being able to step backwards if you need to, to restore where you were as of at any point in time.
A deploy with fault tolerant scalability, meaning that anything can go down and it will keep running.
#### LangSmith
Lang Smith to monitor what's going on in your Lang graph graph.

<img width="935" height="1006" alt="image" src="https://github.com/user-attachments/assets/42daec7d-874f-48d6-92ba-ee26c173c211" />

#### LangGraph
<img width="657" height="671" alt="image" src="https://github.com/user-attachments/assets/d71a941b-dc43-4b5a-9258-a4b4cbdafe67" />
<img width="540" height="597" alt="image" src="https://github.com/user-attachments/assets/d11d7255-8014-4336-9701-e4ca16e35210" />
<img width="552" height="557" alt="image" src="https://github.com/user-attachments/assets/75193b6a-2599-4445-88da-a906d5e55b2c" />

#### AutoGen - Microsoft
<img width="633" height="605" alt="image" src="https://github.com/user-attachments/assets/bce1006a-76d6-4f98-96b0-7d3e0035e5fd" />
<img width="512" height="565" alt="image" src="https://github.com/user-attachments/assets/cc7efa4a-6d8b-43d9-861d-b9d68eedbba2" />
<img width="575" height="420" alt="image" src="https://github.com/user-attachments/assets/b322dc8c-9d33-4a36-92ab-e692f5738641" />

#### MCP - Model Context Protocol
<img width="718" height="625" alt="image" src="https://github.com/user-attachments/assets/c0b6e3dd-9705-4c49-8950-024d7b7d3810" />
<img width="450" height="497" alt="image" src="https://github.com/user-attachments/assets/ab16bf50-32d2-4784-93aa-7e3f941739b2" />
<img width="532" height="467" alt="image" src="https://github.com/user-attachments/assets/e27d9fc9-3026-49d2-bd75-9581ca5d53e0" />

#### LLM Engineering Building Blocks
<img width="881" height="457" alt="image" src="https://github.com/user-attachments/assets/0c6d81c3-87af-47ca-9521-ed29bb524a85" />

##### Closed Source Frontier LLM
GPT from OpenAI
Claude from Aunthropic
Gemini from Google
Grok from X.ai

##### Open Source LLM
Llama from Meta - 1st model
Mixtral from Mistral
Qwen from Alibaba Cloud
Gemma from Google
Phi from Microsoft
DeepSeek from DeepSeek AI (Famous when launched due to low costing around 4M$ for training the model)
GPT-OSS from OpenAI

<img width="860" height="460" alt="image" src="https://github.com/user-attachments/assets/44fcbfc3-43fe-452e-a2d2-6161afeb53ab" />
#### What is Transformers
- The Transformer is a type of neural network architecture that has become foundational in the field of natural language processing (NLP) and beyond. Introduced in the paper "Attention is All You Need" by Vaswani et al. in 2017, the Transformer model has revolutionized how we approach tasks like translation, text generation, and more.
<img width="917" height="427" alt="image" src="https://github.com/user-attachments/assets/ae300bbc-d6e9-4075-95a7-fcd5de551a50" />

##### Parameters and tokens in LLM
Parameters determines how big is LLM. Its from millions to trillions of parameters. More the parameter more the size and intellegent llm be. Its only defined how much data it trians on.
Tokens - When we send a text to llm, it creates a tokens out of it. each word or half of the word can be the token. Less common words (and invented words) get broken into multiple tokens.
LLM api cost is based on number of input tokens and number of output tokens.
<img width="892" height="286" alt="image" src="https://github.com/user-attachments/assets/3007555e-945a-43b5-b2e1-a810e8b9a52f" />

#### Prompt
- In System Prompt, Establish the ground rule like "If you don't know the answer, just say so". Provide critical background context. Add expertise to the prompt
- Context, During the conversation, insert context to give more relevant background informartion pertaining to the topic
- Multi Short Prompting, In prompt provide example for specific scenario, train it.
- To use cache token, give the static prompt first and then the dynamic one, as a result LLM api's call cost you less.
- You can add conditional prompt in the system prompt based on the user message, it will reduce sending extra tokens always to the api.
example given below. Not a proper way to use it. instead we use RAG
<img width="1460" height="380" alt="image" src="https://github.com/user-attachments/assets/bbfda52b-db90-4cd4-9fc5-9a372e7e2ee5" />
- 
  <img width="1331" height="182" alt="image" src="https://github.com/user-attachments/assets/e120d3ac-a38d-4cae-b90a-905805a6c42e" />
#### Hugging Face
- Hugging Face is a leading open-source platform and community for AI, acting as a "GitHub for Machine Learning" where users can share, discover, and collaborate on models, datasets, and demos
<img width="1126" height="670" alt="image" src="https://github.com/user-attachments/assets/2d0b27f1-322b-464d-8bd1-85b794f09c32" />

#### Google Colab
<img width="800" height="678" alt="image" src="https://github.com/user-attachments/assets/f12df2d6-825d-446c-a3df-365535e22d78" />

