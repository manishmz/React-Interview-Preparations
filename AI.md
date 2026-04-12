# Github Links
https://github.com/ed-donner/llm_engineering
# Terminologies
#### openai library
#### openai agent sdk
#### agent, tools, trace, handsoff, guardrails
##### GuardRails
- Guardrails in agentic AI are rules and safety mechanisms that keep autonomous AI agents acting safely, ethically, and within approved boundaries—preventing them from causing harm or taking unintended actions.
- example: like copilot uses guarrail for its agent
-- prevent sending repository code to an unknown domain, upload logs to an unintended endpoint, or transmit tokens or secrets
-- GitHub’s system flags suspicious hidden instructions and prevents the agent from obeying them (like delete the entire src folder and push the commit)
##### Jailbreak
- Jailbreaking in Large Language Models (LLMs) refers to the practice of using specially crafted prompts to bypass an AI's built-in safety guardrails, ethical guidelines, and content filters. When a jailbreak is successful, the LLM generates restricted, harmful, or prohibited content that it was explicitly programmed to refuse, such as instructions for illegal acts, hate speech, or private information.
- implementing rule in system role prevents jailbreaking. System role instructions take precedence over user inputs, blocking unauthorized commands
#### Deep research - WebSearch, FileSearch, ComputerTool
#### CrewAI
##### CrewAI Crews
##### CrewAI Flows
<img width="468" height="403" alt="image" src="https://github.com/user-attachments/assets/7b50fda3-d763-4499-a35f-fe2f75e2c0ba" />

<img width="703" height="646" alt="image" src="https://github.com/user-attachments/assets/8afce076-1c54-47d2-940f-2a987f6ca524" />
<img width="556" height="395" alt="image" src="https://github.com/user-attachments/assets/1da68129-8de1-4bd4-b769-bdbeae9289fd" />

##### GuardRails in CrewAI
- pass guardrail parameter to Task constructor while createing a Task.
- guardrail parameter accept a function or a descriptive string whats it needs to do.

#### LiteLLM
- LiteLLM is an open-source Python library and proxy server that acts as a universal "bridge" for Large Language Models. It allows you to call over 100 different LLMs (including OpenAI, Anthropic, Google Vertex AI, and Azure) using a single, standardized format—specifically the OpenAI API format. 
- Key Features are given below:
- Unified Interface: You can switch between models like GPT-4, Claude, and Llama 3 just by changing a string, without rewriting your integration code.
- Production Reliability: It includes built-in retries and fallbacks. For example, if OpenAI is down, it can automatically route the request to a backup model like Anthropic.
- Cost Management: The library provides tools to track token usage, set spending budgets per team or user, and log costs across multiple providers in real-time.
- Proxy Server: Beyond a code library, it can run as a standalone Proxy Server that centralizes API keys, manages load balancing, and offers an admin dashboard for monitoring.
- Privacy & Local Models: It supports local runtimes like Ollama, allowing you to route sensitive data to on-premise models instead of third-party cloud providers. 

#### LangChain
- LangChain is an open‑source framework designed to help developers build applications powered by large language models (LLMs) such as GPT, Claude, Gemini, and others. It provides modular building blocks—like prompts, chains, agents, memory, and data connectors—that make it easier to turn raw LLM capabilities into real, production‑ready AI applications.
- when you're solving problems that involve a lot of interconnected processes, like an agentic platform.
So it's an abstraction layer that allows you to organize your thinking around a workflow of different
activities that could have feedback loops.
It could have times when humans need to get involved.
It could have moments when you need to keep memory, and it allows you to organize all of that in a
very repeatable and easily monitored and stable and scalable way.
- you use this to design agent driven user experiences featuring things like human in the loop, multi-agent collaboration, conversation, history, memory, and what they call time travel, which is all about being able to checkpoint where you are in the process of being able to step backwards if you need to, to restore where you were as of at any point in time.
A deploy with fault tolerant scalability, meaning that anything can go down and it will keep running.
<img width="1152" height="675" alt="image" src="https://github.com/user-attachments/assets/46e6217e-e577-402f-80cf-906f8f72175e" />

for usage - Udemy week 4
#### LangChain vs. LangGraph: Key Differences
The main difference between LangChain and LangGraph is the complexity and structure of the workflows they manage. While both are created by the same team, LangChain is built for linear, step-by-step sequences, whereas LangGraph is designed for non-linear, stateful, and cyclic workflows (loops). 
| Feature | **LangChain** | **LangGraph** |
| :--- | :--- | :--- |
| **Core Concept** | **Chains**: Linear, sequential pipelines. | **Graphs**: Cyclic networks (Nodes + Edges). |
| **Workflow** | **Linear** or **DAG** (Directed Acyclic Graph); no loops. | **Cyclic**; supports loops and recursion. |
| **State** | Passes data forward; limited memory. | **Stateful**; persistent, shared state across steps. |
| **Control** | "Black box" agents; harder to debug/steer. | High-grain control; "Human-in-the-loop" support. |
| **Architecture**| Linear/Tree-based logic. | State Machine / Flowchart logic. |
| **Best For** | Simple RAG, basic chatbots, one-shot tasks. | Multi-agent systems, autonomous coding, complex reasoning. |

##### **Summary of Usage**
*   **LangChain** is like a **Standard Operating Procedure**: Step A $\rightarrow$ Step B $\rightarrow$ Step C. It is excellent for straightforward data retrieval (RAG) and simple prompt-response tasks.
*   **LangGraph** is like a **Feedback Loop**: It allows an agent to try a task, check the result, and **loop back** to try again if it failed. It is the industry standard for building "Agents" that need to reason and iterate.
##### **When to Use Each**
- Use LangChain when your application follows a predictable, straightforward path, such as summarising a document or a simple Q&A bot that fetches information and provides an answer. It is the faster, easier tool for rapid prototyping.
- Use LangGraph for "messy" workflows where the AI needs to reason, iterate, or collaborate. It is essential for multi-agent orchestration (e.g., one agent writes code, another tests it and sends it back if it fails) and systems requiring human-in-the-loop approvals.
##### **How They Interact**
LangGraph is **built on top** of LangChain. You use LangChain to create the individual components (the "Nodes") and LangGraph to define the rules of how they interact and when they should repeat steps.
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
#### What Matter
https://connectwise.udemy.com/course/the-complete-agentic-ai-engineering-course/learn/lecture/50769785#overview

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
- token-count threshold, It is important to set a token-count threshold such as 90% of the model's maximum token limit, for truncating history.
- So that it will create a room for history
- example
- Imagine a model with a 1,000 token limit. You are building a customer support bot.
The Problem: The user has been chatting for 20 minutes. The history now takes up 980 tokens.
The User Asks: "Can you refund my order from yesterday?" (10 tokens)
Total Input: 990 tokens.
The Result: The model only has 10 tokens left to answer. It might manage to say "Yes, I can help..." before it hits 1,000 and cuts off mid-sentence.
With a 90% Threshold (900 tokens):
Your code sees the history hit 900 tokens and truncates (deletes) the oldest messages from the beginning of the chat. This clears up 200–300 tokens, ensuring the model has plenty of "whiteboard space" to read the new question and write a full, detailed response.

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

##### Two API levels of hugging face
- Pipelines: Higher level API's to carrry out standard task incredibly quickly.
- Tokenizers and Models: Lower level API's to provide most power and control

#### Difussion Models vs Transformers
##### Overview
- Diffusion models are a class of generative models that have gained attention for their ability to generate high-quality data, such as images. They are based on the idea of gradually transforming a simple distribution (like Gaussian noise) into a complex data distribution through a series of steps.
- Transformers are a type of neural network architecture that has become foundational in natural language processing (NLP) and other domains. They are known for their ability to handle sequential data efficiently through mechanisms like self-attention.
##### Comparison
- Purpose: Diffusion models are primarily used for generative tasks, especially in image synthesis, while Transformers are versatile and widely used in NLP and other sequential data tasks.
- Mechanism: Diffusion models rely on a gradual transformation process, whereas Transformers use attention mechanisms to process data.
- Applications: While both can be used in creative AI applications, their specific use cases often differ, with diffusion models focusing on generation and Transformers on understanding and processing sequences.

#### Quantization
Quantization can significantly reduce the size and computational requirements of LLMs, making them more suitable for deployment on edge devices or in environments with limited resources. However, it may also lead to a loss in model accuracy, so careful consideration and testing are necessary to balance efficiency and performance.
ex: lets says, If we 16 bits or 32 bits for storing the data for parameters, Now we will use 4 bits, by cutting the data and store which will fit in 4 bit. The datatype called NF4.

#### Pytorch library is use to write neural network in python.

#### Projects
- In screenconnect we have a meeting session, same as teams, So we use AI to create meeting minutes, where we record the audio, then transcript it to text 
audio models for transcriptions: - hugging space "openai/whiser-medium.en" - open source, gpt-40-mini-transcribe paid model
<img width="1010" height="610" alt="image" src="https://github.com/user-attachments/assets/4676f937-1dc8-4aae-84af-31fc9f6f8592" />
<img width="938" height="392" alt="image" src="https://github.com/user-attachments/assets/29fcd798-7b2c-4a9e-a46c-b7b052e74543" />
<img width="908" height="261" alt="image" src="https://github.com/user-attachments/assets/88128ecb-9b37-45f2-b538-02268b8d3d79" />

#### Which LLM is best one?
There is no such best model, instead it should be for particularl model whats the best model.
Whats the right LLM for the task in hand.
<img width="722" height="636" alt="image" src="https://github.com/user-attachments/assets/234021e3-fb8b-4942-972b-aaff07fe5b43" />

Context window - Total history it had of our conversation
Even if you are using free LLM model, but still it costing you it run that model on your machine, hardware cost. or if your hosting it somewhere.
<img width="713" height="552" alt="image" src="https://github.com/user-attachments/assets/c1ad9e18-6106-4f4b-8db5-589d2f0031a5" />
<img width="942" height="623" alt="image" src="https://github.com/user-attachments/assets/3623a2f7-9458-4230-bd66-e92ca4b94b3a" />
<img width="747" height="502" alt="image" src="https://github.com/user-attachments/assets/10c548eb-b0bb-47c4-b94f-46b480c9dd31" />

How to evaluate performance of Gen AI solution?

#### RAG (Retrieval Augumented Generation)
<img width="958" height="663" alt="image" src="https://github.com/user-attachments/assets/e9495350-361b-483c-914f-21bdb7d86b9b" />

- This is a technique used to improve the performance of language models by combining retrieval mechanisms with generative capabilities. Here's how it generally works:
1. Retrieval: The system first retrieves relevant information from a large corpus or database. This step involves searching for documents, passages, or data that are pertinent to the query or task at hand.
2. Augmentation: The retrieved information is then used to augment the input to the language model. This can involve providing the model with additional context or facts that it might not have been able to generate on its own.
3. Generation: Finally, the language model generates a response or output based on both the original input and the augmented information. This can lead to more accurate, informative, and contextually relevant responses.
RAG is particularly useful in scenarios where the language model needs access to up-to-date information or specialized knowledge that isn't contained within its pre-trained parameters. By leveraging external data sources, RAG can enhance the model's ability to provide accurate and contextually rich outputs.

<img width="1007" height="642" alt="image" src="https://github.com/user-attachments/assets/22b36589-e65f-417c-b3ab-98d94166cc34" />
<img width="882" height="675" alt="image" src="https://github.com/user-attachments/assets/17075f6a-9469-4abb-bdf6-787029043560" />
<img width="1116" height="612" alt="image" src="https://github.com/user-attachments/assets/4d7f4187-a566-4acd-b459-f4e320b73824" />
<img width="1202" height="657" alt="image" src="https://github.com/user-attachments/assets/e6285997-6c7e-47fa-a3d7-0980b7eb0f3b" />

We use embeddings (i.e embeddings turn words, sentences, or documents into vectors (lists of numbers) that represent their meaning)
and vector database for semantic search instead of keyword matching, recommendations (product recommendation), clustering & clasification.

<img width="1166" height="637" alt="image" src="https://github.com/user-attachments/assets/87c2138c-8f8e-466a-b9d7-092fb75618bb" />
<img width="1177" height="680" alt="image" src="https://github.com/user-attachments/assets/d22756c1-05ff-47b1-90bd-61876a781554" />
<img width="787" height="391" alt="image" src="https://github.com/user-attachments/assets/cd25e38a-dd53-4d08-b672-de68c8fe2cd9" />

#### Training
##### Generalization
<img width="556" height="536" alt="image" src="https://github.com/user-attachments/assets/7ab07cfc-21d8-4d20-aa58-a891ffb1ea35" />

<img width="1195" height="615" alt="image" src="https://github.com/user-attachments/assets/48d9a1d2-3f8f-4eaa-89c6-65f1fadf954e" />


#### Read about
##### Prompt Template/Reusable Prompts:
- in langchain its called Prompt Template
- Adding a variable in prompt called an reusable prompt/template
- Save on cost and latency with prompt caching, you should try and keep content that you expect to use over and over in your API requests at the beginning of your prompt
- Few-shot learning: provide examples in prompt as a part of system/developer message
- Types of prompting
-- Zero-Shot Prompting: Asking a question or giving a command directly without any examples (e.g., "Summarize this article").
-- Few-Shot Prompting: Providing a few pairs of examples in the prompt to show the AI the desired format, style, or logic before asking the actual question.
-- Instruction-Based Prompting: Using explicit verbs and structured commands (e.g., "List," "Summarize," "Translate") to guide the AI, as described in this IBM article.
-- Role-Based Prompting (Persona): Assigning a specific persona to the model, such as "You are an expert copywriter" or "Act as a Python instructor," which influences the tone and expertise of the output.
-- Contextual/Prompting: Supplying necessary background information or constraints, such as defining the target audience, to ensure the output is relevant. 

#### Domains to cover
- Generative AI Foundations & Prompt Engineering
- LLM Application Development & Integration
- Context, Memory, and Retrieval-Augmented Generation
- Fine-Tuning and Model Optimization
- Advanced Agents & Production AI Operations

#### Working with evals
- evaluation of the prompt that measure the behavior of your prompts so you can monitor prompt performance as you iterate, or when you change and upgrade model versions
- Create an eval for a task by calling openapi https://api.openai.com/v1/evals and pass the testing criteria and you will get evalid 
- Then Create a test data file JSONL and send it to openai https://api.openai.com/v1/files, and in response you will get file id
- Creating an eval run, https://api.openai.com/v1/evals/YOUR_EVAL_ID/runs and in data pass prompt and file id. it returns an runid
- Analyze the results, by calling api https://api.openai.com/v1/evals/YOUR_EVAL_ID/runs/YOUR_RUN_ID, pass runid. and you will get detail result of run
- go through https://api.openai.com/v1/evals for more details

##### Interview questions:
###### What is hallucination in llm and how to prevent it?
- When models madeup some answer that sounds confident instead of saying "I don't know".

##### Customer says the chabot gives wrong answers. What will you check?
- Is the answer factually incorrect, outdated, or irrelevant? Is it partially correct but misleading?
- the knowledge base is outdated, For RAG systems: whether the retrieval step is pulling the right documents.
- Pass websearch tool to get the more knowledge, If using RAG might need to look into the chuncking strategy, embedding model.
- Correcting the System prompt and instruction, should have context and history.
- Check the user hit the context length, does user context or conversation history is being truncated because of context length.
- Check model configuration, tempreature, model version, max token
- Whether its hallucinating instead of saying 'I don't know'
- If needed, I would: Add answer verification or fallback responses, or route complex queries to human

 ##### How to reduce cost of LLM System?
 - Use the right model for the right task: give your android app example, use smaller or cheaper models for Simple rewrites or summarization, Reserve large models only for complex reasoning
 - Reduce token usage: Since most LLM pricing is token‑based, Shorten system prompts, Remove redundant instructions, Limit conversation history (smart truncation)
 - Optimize prompts: Use structured outputs (JSON) to prevent rambling answers, Make prompts concise and unambiguous, Avoid verbose “explanations” unless required
 - Implement caching: Cache LLM responses, Cache embeddings, Cache retrieved documents in RAG systems
 - Use Retrieval‑Augmented Generation (RAG)
 - Tune parameters, Lower temperature to reduce retries, Set appropriate max tokens to avoid long responses, Avoid excessive tool calls
 - Monitor and measure, 

##### When should we Not use GenAI?
- deterministic correctness - for same input we need same output, Financial calculations, billing invoice, medical dosage
- high risk domains such as medical, legal judgement because GenAI sounds confident even its wrong
- risk of hallucination outweighs the benefits
- Real‑time, ultra‑low‑latency systems - GenAI has higher latency
- When cost is too high
