---
title: "Event 4"
date: 2024-01-01
weight: 4
chapter: false
pre: " <b> 4.4. </b> "
---
# SUMMARY REPORT: AI-POWERED CONVERSATIONAL ORDERING SOLUTION

### Project Objectives

* **Resolve app-switch friction:** Customers often lose interest when forced to leave their active chat stream to download a new app, log in, and register an account just to order food.
* **Overcome legacy AI hallucination errors:** Learn from McDonald's AI failure when it misidentified customer intent and erroneously ordered hundreds of chicken nuggets.
* **Build a seamless multi-channel AI ordering assistant:** Deploy AI ordering across familiar messaging channels (e.g., Zalo, WhatsApp), enabling customers to order food directly during natural messaging.

## Speakers

* Members of **One Team** - First Prize Winners at the FCAJ x Agentic AI Build Week event.

## Key Highlights

### Problems with Current Ordering Systems

* Traditional applications have complex menus and heavy advertisement popups that slow down user onboarding.
* Legacy AI lacks an understanding of natural conversation nuances, easily registering wrong orders when customers abruptly alter their preferences at the last minute.

### AI Conversational Ordering Solution

* **Zero Friction:** Customers chat directly with the brand (e.g., KFC) over familiar messaging platforms like Zalo without downloading apps or creating new accounts.
* **Operational Mechanism:** AI automatically parses customer intent, asks clarifying questions, adds items to cart, and suggests promo code applications.

### Flexible & Cost-Effective System Architecture

* **Adapter Pattern:** Uses a "Channel Adapter" to ingest messages across various channels and normalize them before sending to the AI core. This allows scaling to other platforms (such as Jollibee, Facebook) without rebuilding the system.
* **Power of Agent Core:** Utilizes Amazon Bedrock Agent Core instead of pure Lambda due to its built-in long-term Memory, enabling the AI to recall past order history for better customer service.
* **Ultra-Low Cost:** Serverless architecture achieves 3-5 seconds latency at ~0.006 USD per order, cutting standard infrastructure costs by up to 60%.

## Key Takeaways

### Design Mindset (Business-First)

* **Verification Mechanism:** AI takes orders but always sends a final summary for customer confirmation to prevent incorrect orders.
* **Human-in-the-Loop:** Incorporates a Staff Dashboard so restaurant employees can monitor live AI chat histories and intervene immediately if errors occur.

### Technical Architecture

* Scrapes data automatically using third-party tools like Tiny Fish from official KFC websites to keep menus up-to-date without needing direct brand APIs.
* Understands ingress WAF firewall layers to protect system traffic during sudden surges.

### Hackathon Lessons (Teamwork)

* **Power of Diversity:** A 5-member team of strangers with language barriers (Indian accent, American accent, non-English speaker) collaborated with high efficiency.
* Under extreme time pressure, creating a clear Architecture Diagram was essential to convince judges within a few minutes of pitching.

### Work Application

* **Memory-enabled Models:** Integrate Agent Core into internal chatbot projects to preserve long-term context across sessions.
* **Adapter Architecture:** Apply Adapter Pattern in multi-input systems for data normalization and effortless scaling.
* **Product Mindset:** Build operational monitoring tools (Staff/Admin Dashboards) alongside AI features so systems deliver tangible business value.

## Event Experience

### Learning from Winning Teams

* Realized that a great idea isn't about cramming complex tech, but solving real user pain points (e.g., app download friction).
* Analyzing big tech failures (McDonald's) as a premise for a new solution is a powerful pitching technique.

### Hands-on Technical Experience

* Witnessed a smooth Multi-channel Generative AI system triggering direct actions/tools (cart additions, promo code usage).

### Networking & Hackathon Spirit

* Inspiring atmosphere watching developers work through the night (until 3-4 AM) to deliver impressive solutions.
* Reaffirmed the message: In the AI era, the most critical factor is the ability to "Roll together" — collaborate and lower ego to build a unified product.

#### Some event photos

* ![alt text](/images/4-EventParticipated/4.4-Event4/image.jpg)
* ![alt text](/images/4-EventParticipated/4.4-Event4/IMG.png)

> Overall, Event 4 provided valuable practical insights and strong creative inspiration through One Team's First Prize winning AI-Powered Conversational Ordering solution.
