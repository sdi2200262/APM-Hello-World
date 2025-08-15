# APM v0.4 - Agentic Project Management Framework

**A Structured, Multi-Agent Workflow System for Complex Project Execution with AI Assistants**

## What is APM?

Agentic Project Management (APM) is a multi-agent workflow for managing complex projects within an AI IDE environment. It applies real project management principles to AI workflows like task breakdown, role assignment, progress tracking, and seamless handoffs between team members.

APM utilizes chat sessions in your AI IDE as separate agent instances, each with its own context scope and memory. This allows for more focused interactions and reduces the cognitive load on any single agent.

Dividing the project workload among multiple agents minimizes the risk of context loss and reduces hallucinations, leading to more reliable and consistent results.

## The Problem APM Solves

Working with AI assistants on large projects often feels chaotic. You start with a simple question, and before you know it, you're 50 messages deep in a conversation where the AI has forgotten your original requirements, contradicts its earlier suggestions, or starts hallucinating details that never existed.

These issues arise from fundamental limitations of LLMs: **Context Window Limits**

This constraint feels "heavier" within AI IDEs, when often times Context Windows are shrunk even further to maintain profitable interactions with the model's provider. As conversations grow, the AI struggles to keep track of everything, leading to confusion, errors, and wasted time.

APM addresses these issues by providing a clear framework that prioritizes structured interaction, explicit context management and integration, and efficient, targeted communication with AI assistants through meta-prompting.

## APM's Approach

The framework uses multiple AI agent instances, each with a specific role and clear responsibilities, coordinated through structured protocols and persistent memory/context management.

The result is a workflow that feels more like working with a well organized team than wrestling with a single overloaded AI assistant.

> Think of APM like running a software development team. You have a project manager who understands the big picture, developers who focus on specific tasks, and clear documentation that keeps everyone aligned. Developers document each task execution, and the manager reviews the logs for coordination. The difference is that your "team members" are AI assistants in separate chat sessions.

---

## Multi-Agent Coordination

APM v0.4 employs a sophisticated multi-agent system built around four specialized agent types:

*   **1. Setup Agent:** Initiates the project session, creating the needed APM assets. The Setup Agent conducts comprehensive project discovery, transforms requirements into a detailed Implementation Plan, and initializes the Memory System that enables effective coordination. Once session is initialized it passes control to the Manager Agent.

*   **2. Manager Agent:** Coordinates the project session and makes all the important decisions. The Manager Agent maintains the big picture, creates targeted task assignments for Implementation Agents, reviews completed work, and orchestrates the overall project flow while preserving context continuity between agent instances.

*   **3. Implementation Agents:** Execute focused task assignments by the Manager. Task domains vary: coding, design, analysis, writing, research etc. while Implementation Agent instances are assigned groups of same-domain tasks. They always log their work to preserve context and ensure project continuation.

*   **4. Ad-Hoc Agents:** Temporary agents for isolated tasks (e.g., debugging, research, analysis) outside the main workflow as workflow "branches". They run in separate chat sessions with minimal scoped context, are assigned by Implementation Agents, and return findings for integration. Ad-Hoc Agents don’t make project decisions, just solve a specific problem, report back, and close, preventing context overload in core agents.

> Agent types in APM are **not specialized "personas"**. Their specialization comes from well defined responsibilities and carefully scoped context for each agent instance. Modern LLMs already adapt to user requests by employing specialized sub-models; APM builds on this strength, enabling precise and effective task execution through focused, strategic agent interactions.

### Context Management
APM preserves context with a carefully designed adaptation of the traditional Memory Bank and a context Handover Procedure. For tasks that require isolated, context-intensive work (such as research or debugging), Ad-Hoc Agent instances handle these activities separately, preventing unnecessary strain on the core agents' context.

*   **Dynamic Memory Memory Bank**: An adaptation of the traditional single-file Memory Bank that maps Memory Log files to the tasks of the Implementation Plan. For complex projects Memory Logs are stored in a directory structure with folders mapped to the phases of the Implementation Plan. For simple projects, a single-file traditional Memory Bank is used.

*   **Ad-Hoc Agent Delegation**: Workflow branches for handling debugging, research, or analysis tasks through temporary agents instances that work in isolated context scopes.

*   **Handover Protocol**: A context transfer mechanism using structured handover files and prompts to seamlessly transition between agent instances when context limits are reached.

## The APM Workflow

APM v0.4 operates through two workflow phases & Handover Procedures:

1. **Setup Phase**: Comprehensive project discovery and planning through the Setup Agent & initialization of session assets
2. **Task Loop Phase**: Coordinated task assignment & execution via Manager and Implementation Agents
3. **Handover Procedure**: Seamless context transfer when agents approach memory limits

---

## Core Framework (`/prompts`)
- `/prompts/Setup_Agent/`: Initialization Prompt & Context Synthesis Prompt for the Setup Agent
- `/prompts/Manager_Agent/`: Initialization Prompt & Handover Guide for the Manager Agent
- `/prompts/Implementation_Agent/`: Initialization Prompt & Handover Guide for the Implementation Agents
- `/prompts/ad-hoc/`: Initialization Prompt & Delegation Guides for Ad-Hoc Agents
- `/prompts/schemas/`: Schemas of JSON asset format variants for the Implementation Plan, Memory Logs & Task Assignment Prompts plus README, examples & schema validation python script 
    > **Testing Preview:** JSON asset format variant is designed for "token-wealthy" Users unconcerned with token consumption, or APM contributors seeking to experiment and provide feedback on asset structure and parsing efficiency. Experimental only; not suitable for production or resource-constrained use due to much higher token consumption
- `/prompts/guides/`: Standby guides that Agents read to understand APM processes and protocols in project breakdown, memory management, task assignment, review, and handover procedures.

## Documentation (`/docs`)  
The `/docs` directory contains comprehensive documentation covering the APM framework, including agent roles, workflow processes, memory management strategies, prompt engineering techniques, and optimization tips to help you effectively implement and customize APM for your projects.

1. **Understand the Agents**: Read `Agent-Types.md` to learn about Setup, Manager, and Implementation Agent roles and Ad-Hoc Agent Delegations
2. **See the Big Picture**: Read `Workflow-Overview.md` for a complete process walkthrough  
3. **Start Your First Project**: Follow the instructions in `Getting-Started.md` to initiate your first APM session
4. **Optimize Your Approach**: Review `Token-Consumption-Tips.md` for efficiency strategies and `Modifying-APM.md` for customizing APM assets to match your needs
5. **Deep Understanding (Advanced):** Read `Context-and-Memory-Management.md` and `Context-and-Prompt-Engineering.md` to get a complete understandinng of how APM utilizes context, memory and cross-agent communication. If you wish to contribute to APM, consider reading these two documents first.

---

APM is an Open Source project, and contributions to both the framework and its documentation are encouraged. You can contribute by posting an Issue for bugs, feature requests, or questions, or by submitting a Pull Request (PR) with improvements, fixes, or documentation enhancements/refinements. For details on contributions and guidelines, please see the [CONTRIBUTING.md](../CONTRIBUTING.md) file.