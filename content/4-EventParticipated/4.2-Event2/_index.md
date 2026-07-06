---
title: "Event 2"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 4.2. </b> "
---
# SUMMARY REPORT: AUTOMATED PROMPT ENGINEERING: ENHANCING LLM OUTPUT QUALITY

### Event Objectives

* Share the art of communicating with AI (The Art of Communicating with AI) and how to improve the output quality of Large Language Models (LLMs).
* Emphasize the importance of Prompt Engineering and the negative impacts of poor prompt construction.
* Provide core components, principles, and techniques from basic to advanced for interacting effectively with LLMs.
* Introduce "Proptimizer" - a solution to automate prompt optimization along with its system architecture running on the AWS cloud.

## Speakers

* **Nguyen Tuan Thinh** - DevOps/Cloud Engineer, First Cloud AI Journey.

## Key Highlights

Negative impacts of poor prompt construction
* **Generic results:** Using generic prompts will only yield generic outputs.
* **Wasted cost:** Inefficient token usage due to unoptimized prompts increases AI utilization costs.
* **Lack of consistency:** Ambiguous instructions lead to inconsistent AI outputs.
* **Reduced productivity:** Poor communication with AI wastes time and reduces work efficiency.

Transition to standard prompts (Great Prompt)
A great prompt should include the following core components:
* **Role:** The persona the AI needs to adopt (e.g., Career Consultant).
* **Instruction:** The specific task the AI must execute.
* **Context:** Relevant background information.
* **Input Data:** The data or text to be processed.
* **Output Format:** The structure, format, and tone of the output.
* **Examples:** Sample inputs and outputs (few-shot prompting) for the AI to emulate.
* **Constraints/Guidelines:** Length limitations, things to focus on, or things to avoid.

Token Economics
* **Nature of Tokens:** LLMs read and generate text based on "tokens" (units smaller than words, not always a full word). Token counts vary depending on the language used.
* **Cost Discrepancy:** Input token costs are cheaper than output token costs. (For reference: Input tokens are \$5.00/million tokens, while Output tokens are \$25.00/million tokens).

Advanced Prompting Techniques
* **Chain-of-Thought (CoT):** Guiding the AI to reason step-by-step.
* **Self-Consistency:** Combining CoT with multiple reasoning paths and selecting the most common, logical answer.
* **Tree-of-Thoughts (ToT):** Reasoning in a tree structure to evaluate multiple paths.
* **Retrieval-Augmented Generation (RAG)** and **Role Prompting** techniques.

Proptimizer Architecture
The Proptimizer solution is a browser extension that automates prompt optimization, built 100% Serverless on AWS with zero idle infrastructure cost (excluding Bedrock services):
* **Frontend & Delivery:** Uses AWS CloudFront (CDN) and Amazon S3 to store static web content.
* **Security & Backend:** Amazon Cognito manages user authentication; Amazon API Gateway routes traffic, and AWS Lambda handles backend logic serverlessly.
* **AI Integration & Database:** Connects to multiple AI models (Claude, GPT) via Amazon Bedrock without training models, storing prompt histories with high speed using Amazon DynamoDB.
* **Monitoring:** Manages logs and performance metrics using Amazon CloudWatch Logs & Metrics.

## Key Takeaways

Design Mindset
* **Clear Communication:** Describe specifically **what to do (DOs)** instead of focusing on what not to do (DON'Ts).
* **System Optimization:** Use delimiters to partition the prompt structure and break long inputs into smaller chunks for the AI to digest easily.
* Allow the AI to answer **"I don't know"** to prevent hallucination, and avoid asking the AI to perform complex math directly.

Technical Architecture
* Mastered the integration of AWS technologies and Generative AI.
* Understood how to use **Amazon Bedrock** as a single API gateway to connect with foundation LLMs to enhance applications easily.
* Designed **DynamoDB NoSQL** databases suitable for high-speed queries with millisecond response times.

Work Application
* **Apply the 7-component prompt structure** (Role, Instruction, Context, etc.) in current projects to achieve the best interaction efficiency with LLMs.
* **Optimize AI Costs (Token Economics):** Write concise prompts, removing redundant words to reduce wasted token costs in daily tasks.
* **Use Advanced Prompting:** Apply the Chain-of-Thought (CoT) technique in tasks requiring logical reasoning or source code analysis.
* **Internal Application Design:** Formulate ideas to build internal AI-integrated assistant tools based on the Serverless architecture (Lambda, Bedrock, S3) referenced from Proptimizer.

## Event Experience

Learning from highly skilled speakers
* The presentation by Nguyen Tuan Thinh offered a unique combined perspective between artificial intelligence (LLM) and cloud infrastructure (Cloud/DevOps), helping me understand not only how to use AI but how to build tools surrounding it.

Hands-on technical exposure
* Visualized the data flow through a multi-step reasoning model using clear diagrams of **Chain-of-Thought** and **Tree-of-Thoughts**.
* Understood in detail the actual architecture flow on AWS from client request submission to model response delivery.

Using modern tools
* Explored the **Proptimizer** concept, an intelligent utility helping to optimize prompts and chat with AI anywhere on the web.
* Realized the power of **Amazon Bedrock** in materializing AI application ideas rapidly.

Networking and discussions
* The event provided a shared reference point between application design (engineering) and model communication (prompting).
* Through practical examples like prompts optimizing recommendations for interns (Career coach), I recognized that prompt engineering is highly practical and immediately applicable to any profession.

## Lessons Learned

* Prompt Engineering skills are today the key to unlocking the full potential of AI; communicating well with AI directly optimizes work efficiency.
* Applying Serverless architectures on AWS for AI products yields excellent benefits in terms of setup costs (\$0) and scalability.

#### Some event photos
* ![alt text](/images/4-EventParticipated/4.1-Event2/image.png)

> Overall, the event not only provided technical knowledge but also helped me reshape my thinking about application design, system modernization, and cross-team collaboration.
