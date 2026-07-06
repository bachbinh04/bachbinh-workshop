---
title: "Event 3"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 4.3. </b> "
---
# SUMMARY REPORT: BUILDING LARGE-SCALE VOICE AI ASSISTANTS (VOICE AGENTS)

### Event Objectives

* Introduce a general overview of the inner workings of Voice AI and how to enable voice communication for artificial intelligence systems.
* Analyze the limitations of current Voice AI for the Vietnamese language and solve the problem of processing natural language in enterprise environments (especially the banking sector).
* Explore architectural standards to bring a Voice Agent from a Proof of Concept (POC) to a production environment.
* Inspire the development of natural, smooth, and secure human-computer communication experiences.

## Speakers

* **Hieu Nghi**
* **Kiet**
* **Trung Do**

## Key Highlights

Selecting language-appropriate AI architectures
* Most current Speech-to-Speech models are only optimized for English. Vietnamese is a low-resource language, so to run efficiently, the system architecture is split into three parts: Speech-to-Text (STT) -> LLM for text processing -> Text-to-Speech (TTS).
* This architecture helps enterprises tightly control AI responses (preventing the AI from hallucinating or saying inappropriate things) and easily execute complex tasks (Tool calling) such as automatically blocking bank cards.

Handling context and communication culture (Context & Culture)
* The system needs the ability to recognize gender from voice to address users (e.g., Mr./Ms.) accurately.
* Handling the "interruption" problem: The AI must be trained to distinguish when a user pauses to think (e.g., pauses while reading a phone number) and when they have finished speaking, avoiding cutting off the customer.
* For regional accents, STT training data needs 10-20% local accents to recognize information well. However, AI responses should maintain standard accents, except for specific use cases like sales or debt collection.

Optimizing speed and going to Production
* Response speed (Latency) is critical. Audio processing, text translation, and LLM execution must be done via a *streaming* mechanism (continuous data flow) to minimize latency.
* Must have a *Human-in-the-loop* mechanism: The system needs to detect when the AI reaches its limit (e.g., when the customer becomes frustrated) to transition the call smoothly to a human agent.

## Key Takeaways

Design Mindset
* A great AI product lies not only in the core technology but also in user experience, understanding behaviors, and natural human communication culture.
* When designing automation systems, always leave a smooth fallback route (handing over to real humans) instead of relying 100% on AI in sensitive customer touchpoints.

Technical Architecture
* Mastered the superiority of the 3-component decoupled model (STT - LLM - TTS) when solving specific language problems.
* Understood the mandatory role of streaming and tool calling mechanisms in transforming AI from a passive Q&A chatbot into an active real-time agent.

Work Application
* **Improving App Experiences:** Apply the STT-LLM-TTS architecture to integrate voice-controlled assistants into cross-platform mobile apps (such as Flutter) connecting with the backend, allowing hands-free interaction for end-users.
* **Optimizing Cloud Infrastructure:** Apply latency optimization and streaming handling principles to develop systems on AWS, combining cloud foundational knowledge to build high-speed, highly resilient automation flows.

## Event Experience

Learning from field experts
* Shared insights from founders and engineers brought a deep perspective on the gap between building a simple AI demo and building an actual production system serving millions of users at major banks.

Hands-on technical exposure
* Observed a live demo of the Voice Agent and understood how engineers resolve complex "pain points" of the Vietnamese language.
* Expanded the vision of the potential of next-generation AI systems when granted execution capabilities via Tool calling, rather than just passive information retrieval.

## Lessons Learned

* Decoupled architecture (STT - LLM - TTS) combined with function calling (Tool Calling) is the optimal solution to overcome the low-resource barrier of Vietnamese and turn AI into active "executors".
* Culturally aware communication experiences (accurate addressing, natural pauses) and fallback mechanisms to humans (Human-in-the-loop) are critical factors for deploying Voice AI in production.

#### Some event photos
* ![alt text](/images/4-EventParticipated/4.1-Event3/image.png)

> Overall, the event not only provided technical knowledge but also helped me reshape my thinking about application design, system modernization, and cross-team collaboration.
