---
title: "Event 1"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---
# SUMMARY REPORT: AUTOMATING WORK WITH AMAZON Q AI ASSISTANT AND MCP

### Event Objectives

* Introduce **Amazon Q**, a user-friendly AI assistant developed by AWS for end-users.
* Resolve time-consuming issues in business operations and reporting.
* Explain the inner workings of AI Agents and how to use the Model Context Protocol (MCP) to allow AI to interact with external applications.
* Inspire developers with product design mindsets focused on solving real-world customer problems.

### Speakers

* **Hai An** - Cloud Consultant at C Pacific Vietnam (Speaker who has presented at AWS Singapore Summit and Silicon Valley).

### Key Highlights

User-Centric Design
* Technical expertise is only one factor; the most critical element in creating a successful product is **solving the user's/customer's problem**.
* AI application automates the process of gathering data to produce weekly reports, saving time for managers and executives (C-level).

Amazon Q Integration Ecosystem
* AWS has built an Agent platform that integrates tightly with popular ecosystems such as **Microsoft** (Word, Outlook, Teams, PowerPoint) and **Google** (Gmail, Calendar).

Concept of Agents and MCP (Model Context Protocol)
* Large Language Models (LLMs) are highly intelligent but **cannot take action independently** (e.g., automatically scheduling an appointment or sending an email).
* To enable AI to interact with the real world, the system requires execution functions (Actions/Functions). This protocol is called **MCP - acting as the "extended arms"** connecting AI with platforms like Gmail, Jira, or Confluence.

Automation via Hands-on Demo Flows
* **Creating Analytics Dashboards:** Users without business intelligence (BI) knowledge can upload a raw Excel file (e.g., sales data), and Amazon Q will automatically create analysis tables and render dashboard charts.
* **Meeting Summarization:** The AI has the capability to transcribe speech to text, automatically summarize key decisions in a meeting, and trigger MCP to send "next steps" report emails to participants.

Security & Compliance
* The platform operates based on the AWS Shared Responsibility Model: AWS manages the infrastructure and foundation models, while users manage their own data and applications.

### Key Takeaways

### Design Mindset
* Technology products must start from **fundamental and close-to-life needs** of people.
* AI system design must go beyond simple question-and-answer (chat) interfaces and aim to transform AI into active "executors" (Agents) that deliver direct operational value.

### Technical Architecture
* Mastered the core concept: **Agent = LLM + Computing Services (Action/Function/MCP)**.
* Understood how the Amazon Q platform combines AI processing with third-party APIs to create complete automation flows.

### Work Application
* **Boosting Individual/Team Productivity:** Use the new Amazon Q Desktop version to quickly process raw Excel data into visual reports without spending time setting up complex BI tools.
* **Process Governance Automation:** Research and develop internal MCP modules to integrate AI assistants with tools used in the company (such as Jira, Microsoft Teams) to automate task tracking and follow-up reminders after meetings.

### Event Experience

Learning from highly skilled speakers
* The presentation by speaker Hai An brought great inspiration. The speaker emphasized that everyone's technical capability is comparable; the difference lies in **confidence** and the ability to collaborate with teammates to build amazing products.

Hands-on technical exposure
* Observed firsthand how the system parses natural language requests (prompts) into structured "system prompts" (including overview, key decisions, action items) so the AI understands its task precisely.
* Saw the great potential of **MCP "extended arms"** in transforming a passive LLM into an active system capable of interacting with emails and calendars.

Using modern tools
* Introduced to the free **Amazon Q** platform, fostering a mindset that developers can write custom MCP servers to extend AI capability depending on their own requirements.

#### Some event photos
* ![alt text](/images/4-EventParticipated/4.1-Event1/image-1.png)

> Overall, the event not only provided technical knowledge but also helped me reshape my thinking about application design, system modernization, and cross-team collaboration.
