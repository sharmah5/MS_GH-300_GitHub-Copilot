# GH-300 GitHub Copilot

### Certification Prep LevelUp

* aka.ms/On-DemandLevelUp
* https://skillupwithlevelup.com/certification-prep-on-demand?solution_areas=81034

### Lab Resources

* Lab link:	https://cloudweeks.learnondemand.net/Class/719908
* Lab key:	9769C925460C9C0E

## Introduction
* We are a software developer, familiar with Git and GitHub, and have some knowledge of AI.
* We want to integrate GitHub Copilot into our development workflows.
* How can we customize Copilot in GitHub to our needs?

## Understand Responsible AI Principles

* When you supply data to these AI tools, what happens to the data?
* There are 6 principles of AI that should be followed.

### Mitigate AI Risks

* You can very rapidly create code against some specification issued to Copilot.
    * Quickly test and deploy to production.
    * Leads to acceleration of release of business software for an organization.
* This version of Copilot is geared towards code generation, not the same Copilot that is available as a chat bot.
* While it is very capable, there is risk.
* We are using tools that are hosted by a third party (Microsoft) and these tools have a certain amount of randomness (hallucinations) and present it as legitimate.
    * And if the tool is not transparent, we don't know how the AI tool arrived at the solution.
* To mitigate risks, we want to implement `Governance Frameworks` to help manage our data and oversee our AI tools.

#### Principles of Responsible AI (Re. GitHub Copilot)

* `Fairness` - AI systems should treat all people fairly, avoiding differential impacts on similarly situated groups.
* `Reliability and Safety` - AI systems must operate reliably, safely, and consistently, minimizing unintended harm and perform as intended
* `Privacy and Security` - Protecting user privacy and data security is crucial, including consent, minimal data collection, anonymization, and strong encryption.
* `Inclusiveness` - AI systems should be accessible and empower everyone, ensuring they work well for diverse users and are available worldwide.
* `Transparency and Accountability` - AI systems must be understandable, with clear explanations, auditability, and continuous monitoring to ensure responsible operations.

## Introduction to GitHub Copilot

* GitHub Copilot can be used with Visual Studio Code, Visual Studio which presents a chat interface.
    * There are integrations with other development tools as well.
* `Copilot for Chat` - allows us to identify code errors and suggest fixes, allows us to generate unit tests.
    * Can also allow us to build an application from scratch
    * Any kind of programming task we can conceive of can be achieved with Copilot for Chat.
* `Copilot for Pull Requests` - You can open a copilot chat interface on GitHub directly.
    * Anything we do day in day out as developers through GitHub can be automated with copilot.
    * Integration suggested changes to code by using Copilot Workspace
    * Can review pull requests, can adjust the suggested descriptions for commits.
* `Copilot CLI` - Can work directly on the command line to chat with Copilot without having to use another application in which Copilot is integrated.

### Subscription Plans

![alt text](./notes_artifacts/images/github_copilot_subscriptions_individual.png)

![alt text](./notes_artifacts/images/github_copilot_subscriptions_business.png)

### Demo

* You can install GitHub Copilot as an extension in Visual Studio Code
* If you have a higher tier license, you need to authenticate against your GitHub account to get those features.
* Crtl-I allows us to provide a prompt to GitHub Copilot in Visual Studio Code that will allow us to use natural language to generate code in particular language
* We need to review the GitHub Copilot documentation to identify what features we can customize - how can we change the behavior of Copilot to work for us?

## Craft Effective Prompts

* `Prompt Engineering`
    * Craft clear instructions to guide AI systems like GitHub Copilot.
    * Ensures code is syntactically, functionally, and contextually correct.
    * Generates context-appropriate code tailored to project needs
* `Principles of Prompt Engineering`
    * Focus on a single, well-defined task or question for clarity.
    * Provide explicit and details instructions for precise code suggestions
    * Keep prompts concise to maintain clarity without overloading the AI.
* `Best Practices in Prompt Engineering`
    * Use descriptive filenames nad keep related files open for rich context.
    * `Iterate` - Refine prompts based on feedback to improve AI responses
    * `Contextualize` - Provide relevant background information to enhance code suggestions.
* `Advanced Strategies`
    * `Layered Prompts` - Break complex tasks into smaller, manageable prompts.
    * `Feedback Loop` - Continuously evaluate and adjust prompts for optimal performance.
    * `Collaborative Input` - Involve team members to ensure comprehensive and effective prompts.

## Engineer Prompts for Performance

* We have a limited number of credits (tokens) that we can use. If we cross, we will need to pay for more.

### GitHub Copilot user prompt process flow.

* `Inbound Flow`
    * We provide a prompt through a `Code Editor`
    * This travels to a `Prompt Server`
    * This server sends the prompt to a `Toxicity Filter` to determine if the prompt is ethical, safe, and can be evaluated.
    * The prompt is then sent to teh `LLM`, where it is tokenized and evaluated
* `Outbound Flow`
    * The `LLM` provides its response
    * This travels back to the outbound `Toxicity filter` to ensure the LLM hasn't provided an unsafe response.
        * This doesn't guarantee the correctness of the response.
    * The response travels to the `Proxy Server`
    * Finally it reaches the `Code Editor` from where we gave the prompt.

* You always want to start a new chat session when changing topics since the LLM will evaluate the entire chat history when addressing your question which will consume more tokens

### GitHub Copilot Data

* `Data Handling for Code Suggestions`
    * `No Retention` - once we get our response, GitHub Copilot discards prompts
    * `Opt-Out Option` - Individual subscribers can opt out of sharing their prompts for model fine-tuning
* `Data Handling for Copilot Chat`
    * `Response Formatting` - formats responses for optimal presentation, highlighting code snippets.
    * `User Engagement` - allows follow-up questions and maintains conversation history for context
    * `Data Retention` - retains prompts and suggestions for 28 days outside code editor

### Copilot LLMs

* LLMs are trained on vast amounts of text from diverse sources
* They generate contextually relevant and coherent text, making meaningful contributions to various forms of communication.
* LLMs are neural networks with millions or billions of parameters, fine tuned to understand and predict text effectively
* These models can be tailored for specialized tasks, making them highly versatile across different domains and languages



![alt text](./notes_artifacts/images/day1_homework.png)
