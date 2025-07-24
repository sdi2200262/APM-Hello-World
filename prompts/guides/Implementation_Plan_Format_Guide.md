# APM v0.4 - Implementation Plan Format Guide
This guide explains how Setup Agents convert simple Implementation Plan files into detailed, structured APM artifacts. Enhanced task details help Manager Agents create precise Task Assignment Prompts, supporting Implementation Agent success. It defines two Implementation Plan variants: 
- Markdown
- JSON
Planning duties are split between the *Setup Agent* and the *Manager Agent*.

## 1. Format Enhancement Overview
Transform simple project decomposition file into detailed Implementation Plan artifact:

**Enhancement Chain:**
- **Simple File** → Basic phases, tasks, agents, dependencies from project decomposition
- **Enhanced Format** → Detailed objectives, concrete outputs, precise guidance, structured formatting, detailed instructions
- **Result** → Manager Agent is able to create highly specific Task Assignment Prompts for Implementation Agent success

**Enhancement Purpose:**
Enable Manager Agents to reference clear deliverables, provide explicit instructions with specific constraints, and concrete context for cross-agent dependencies when creating Implementation Agent task assignments.

## 2. Phase-by-Phase Enhancement Process
Transform simple file content into detailed artifact format **one phase at a time**:

### 2.1. Phase Enhancement Sequence
For each phase in simple `Implementation_Plan.md`file:
- Read current phase tasks, agents, and basic descriptions
- Enhance each task with detailed meta-fields, structured formatting and detailed instructions
- Apply document structure specifications from §3 
- Move to next phase only after current phase enhancement complete

### 2.2. Task Enhancement Requirements
Transform each simple task entry into detailed task block defined in §3.3:

**Objective Enhancement:**
- Convert basic task name into one-sentence goal statement
- Ensure objective reflects concrete achievement, complete unit of work and value delivery  

**Output Specification:**
- Transform simple descriptions into specific deliverables with file paths
- When possible, include concrete artifacts Manager Agent can reference for Task Assignment Prompts

**Guidance Development:**
- Add constraints, requirements, and technical specifications
- Include dependency references in proper format: "Depends on: Task X.Y Output (+ by Agent Z - if cross-agent)" 
- Provide context enabling Manager Agent to create precise Implementation Agent instructions
**Subtask Description Enhancement:**
- For **multi-step tasks**: Expand each sequential step into a clear, detailed, actionable instruction, preserving workflow order and clarifying dependencies.
- For **single-step tasks**: Use an unordered list of concise, detailed instructions sufficient for task completion in one attempt.
- In all cases, ensure subtask descriptions provide enough context and clarity for reliable execution, and maintain the original workflow sequence from the simple file while increasing precision.

## 3. Document Structure Specifications

### 3.1. Document Header (Lines 1‑15)
```markdown
# <Project Name> – Implementation Plan 

**Memory Strategy:**  [Leave empty - determined during Memory Root Creation phase]
**Last Modification:** [Summary of last modification by Manager Agent here]
**Project Overview:** [High-level project overview here]
```
Keep this header < 15 lines so diff tools can catch version bumps cheaply.

### 3.2. Phase Sections
- Use level 2 headings (`##`) for phases: `## Phase <n>: <Name>`.
- Each phase groups related tasks (e.g., refactoring, feature rollout).
- For small or strictly linear projects, omit phases and list tasks directly under the header.

### 3.3. Task Blocks
- Use a level 3 heading (`###`) for each task, assigned to one agent:  
    `### Task <n.m> – <Title> │ <Agent_<Domain>>`
- Each task is a focused, actionable unit of work for an Implementation Agent with one clear objective that delivers independent value.
- Directly under the heading, add an unordered list with these meta-fields:
    - **Objective:** One-sentence task goal.
    - **Output:** Concrete deliverable (e.g., function, module, PR).
    - **Guidance:** Key constraints or special requirements (e.g., library, API contract).

### 3.4. Sub-Task Formatting
Sub-tasks break down a parent task into logical steps and must be included for every task:

**Single-step format [unordered list (`-`)]:**
```markdown
- Do activity/component 1
- Do activity/component 2
- Do activity/component 3
(...)
```

**Multi-step format [ordered list (`1.`, `2.`, ...)]:**
```markdown
1. **Step Name:** Step description with clear action.
2. **Step Name:** Step description with clear action.
3. **Step Name:** Step description with clear action.
(...)
```

### 3.5. Task Dependency Declaration Format
**Producer Task:** Specify concrete deliverables in the `Output` field for consumer task integration
**Consumer Task:** Reference dependency in `Guidance` field using format: `"Depends on: Task X.Y Output (+ by Agent Z - if cross-agent)"`

### 3.6. Phase Summary Format (Manager Agent)
At phase completion, append summaries to Implementation Plan under current phase and before next phase:

```markdown
## Phase <n>: <Name> Summary
> Delivered: Tasks <n.m>, <n.k>
> Outstanding: Tasks <n.x>, ...
> Blockers: ...
> Common Bugs/Issues: ...
> Compatibility Notes: ...
```

## 4. JSON Variant Specification
JSON Implementation Plans follow identical rules and structure as Markdown but use schema validation at `/prompts/schemas/implementation_plan.schema.json`. All requirements for task meta-fields, agent assignments, dependencies, summaries, and policies apply as described above.

## 5. Setup Agent Responsibilities
Transform simple Implementation Plan file into detailed APM artifact:

1. **Variant Selection**
    - Choose MD/JSON based on user preference from Context Synthesis Phase (default: Markdown)

2. **File Enhancement**
    - Read simple Implementation Plan file from project decomposition phase
    - Apply phase-by-phase enhancement process from §2 transforming basic task entries into detailed task blocks with meta-fields

3. **Document Formatting**
    - Apply document structure specifications from §3 creating proper headings, meta-fields, and formatting
    - Validate JSON structure against schema if JSON variant selected

4. **Quality Assurance**
    - Present enhanced plan for user review and feedback ensuring it provides sufficient detail for Manager Agent Task Assignment Prompt creation
    - Iterate based on user input until plan is explicitly approved

## 6. Manager Agent Responsibilities
Maintain detailed Implementation Plan throughout APM session:

1. **Plan Validation & Improvement**
    - Read guide, evaluate plan
    - Validate JSON if used
    - Suggest improvements only for integrity issues
    - Confirm understanding before execution

2. **Live Plan Maintenance**
    - Sync plan with project changes
    - Add/remove/modify phases and tasks as needed
    - Update "Last Modification" for all changes
    - Keep task numbering and dependencies consistent

3. **Execution Coordination**
    - Manage cross-agent handoffs per dependencies
    - Extract producer task outputs, inject into consumer task assignments
    - Issue task prompts per plan

4. **Phase Management**
    - Track phase completion
    - Write detailed phase summaries in Memory Root
    - Add concise phase summaries to plan before next phase following Memory System Guide

---

**End of Guide**