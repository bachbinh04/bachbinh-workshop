---
title: "UI Automation with Amazon Nova Act"
date: 2026-06-05
weight: 2
chapter: false
pre: " <b> 3.1. </b> "
---

# UI Automation with Amazon Nova Act

Automating browser operations has become a crucial part of the software development process. Tasks like UI Testing, Web Scraping, or automating back-office processes all require the browser to precisely replicate user actions.

For years, frameworks like Selenium, Playwright, or Puppeteer have been popular choices. However, these tools rely heavily on XPath or CSS Selectors to locate elements on a webpage. When the UI changes, these selectors often break, leading to code fragility and requiring refactoring of the entire automation script.

Amazon Nova Act was developed to address this limitation by leveraging Agentic AI to control browsers via natural language, rather than depending on the HTML structure.

---

# Limitations of Traditional Web Automation

Current automation frameworks operate by determining the exact position of each element on the interface.

For example:
- Click the login button.
- Type data into the search bar.
- Select a specific menu.

To perform this, developers must use:
- XPath
- CSS Selector
- ID
- Name

The drawbacks of this approach are:
- Any front-end change in the HTML structure or class name can break the entire script.
- The maintenance cost of automation increases significantly as interfaces change frequently.
- Building long workflows becomes difficult to scale.

---

# What is Amazon Nova Act?

Amazon Nova Act is an AI Agent service on AWS that allows controlling web browsers using natural language.

Instead of specifying precise XPath or CSS Selectors, users only need to describe their desired action in English.

For example:

```python
nova.act("Type 'iPhone' into the search bar and press Enter")
```

Nova Act will automatically:
- Identify the search bar.
- Input the data.
- Perform the Enter action.

This process does not depend directly on the website's HTML structure but on the AI model's capability to understand the user interface.

---

# How Nova Act Works

Nova Act is built on the Amazon Nova 2 Lite foundation and trained using Reinforcement Learning in simulated browser environments (Web Gyms).

Instead of identifying elements via XPath, the AI analyzes:
- The visual interface.
- Website layout.
- Context of elements.
- Displayed content on the screen.

Because of this, when minor interface changes occur, the workflow can continue operating without modifying any code.

---

# Workflow of Amazon Nova Act

## Step 1: Experiment on Playground

Amazon provides a Playground that allows users to experience Nova Act directly in the browser.

Users only need to:
- Enter the website URL.
- Describe the request in natural language.

The AI will automatically:
- Open the website.
- Scroll the page.
- Move the cursor.
- Click.
- Enter data.

This helps test workflows quickly without writing any code.

---

## Step 2: Develop using Python SDK

After successful testing, the Python SDK can be used to construct complete workflows.

Installation:

```bash
pip install nova-act
```

Example:

```python
for customer in customer_list:
    nova.act(
        f"Fill name {customer['name']} and email {customer['email']} into register form"
    )

    nova.act(
        "Click Submit button and wait page reload"
    )
```

In the above example:
- Python handles customer list data.
- Nova Act is responsible for interacting with the web interface.

This allows integrating AI capabilities with program logic.

---

## Step 3: Deploy to AWS

After finalizing the workflow, Nova Act supports direct deployment to the AWS infrastructure.

The deployment process includes:
- Packaging the application into a container.
- Storing the image on Amazon ECR.
- Running the workflow on Bedrock AgentCore.
- Creating a dedicated browser sandbox for each session.

This allows scaling the number of workflows without managing browsers or servers manually.

---

# Outstanding Features

## Human-in-the-Loop (HITL)

During automation execution, the AI might encounter situations like:
- CAPTCHA
- MFA
- Account lockouts

Instead of terminating the entire workflow, Nova Act sends a notification to the administrator via Amazon SNS.

The user only needs to handle the authentication step manually, and then the workflow resumes the remaining steps automatically.

---

## Observability

Nova Act provides comprehensive monitoring of the execution process.

Users can review:
- Videos of the automation process.
- Step-by-step screenshots.
- Workflow history.

This makes debugging more visual compared to traditional automation frameworks.

---

## Enterprise Security

The entire workflow executes within AWS sandbox environments.

Additionally, Nova Act supports:
- IAM authorization.
- Session isolation.
- Cookie and session protection.
- Data leakage prevention.

This makes the solution suitable for enterprise environments requiring high security.

---

# When to use Nova Act?

Nova Act is suitable for tasks such as:
- UI Automation Testing
- Web Automation
- Web Scraping
- Automatic Form Filling
- Handling repetitive office tasks
- Building browser-operating AI Agents

Especially, Nova Act is highly effective in projects with frequently changing user interfaces.

---

# Conclusion

Amazon Nova Act introduces a new approach to web interface automation by combining AI Agents with browsers.

Instead of relying entirely on XPath or CSS Selectors, Nova Act allows developers to describe actions in natural language, significantly reducing script maintenance costs when interfaces change.

While Selenium and Playwright remain powerful tools in many scenarios, Nova Act opens a new path for workflows needing high adaptability and deep integration with the AWS ecosystem. It is a worthy choice for QA, DevOps teams, and enterprises building AI-driven automation systems.
