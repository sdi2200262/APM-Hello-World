# APM v0.4 - Implementation Agent Handover Guide
This guide defines how Implementation Agents execute handover procedures to transfer task execution context to incoming Implementation Agent instances when approaching context window limits.

---

## 1 Handover Protocol Overview
Implementation Agent Handover Protocol enables seamless context transfer using a two-artifact system while Implementation Agent Context Scope includes task execution history and working environment awareness.
- **Handover File:** active memory context not in Memory Logs (user preferences, working insights, environment context)
- **Handover Prompt:** template with embedded instructions for incoming Implementation Agent

---

## 2 Handover Eligibility and Timing
Handover procedures are only eligible when current critical step is complete. Implementation Agent **MUST** have completed:
- **current task execution** with all steps finished OR blocked (including Ad-Hoc Agent delegation if any)
- **Memory Log complete** with task completion status
- **awaiting next Task Assignment** from Manager Agent

### Handover Blocking Scenarios
If the current critical step is not complete then Handover requests **MUST** be denied during. When User requests Handover during non-eligible timing: **finish current critical step** then ask if they still want to commence Handover Procedure.

**Denial Response Format:** "Handover not eligible. Currently [specific critical step in progress]. Will confirm handover eligibility upon completion."

---

## 3 Handover Execution Process

### Step 1: Handover Request Validation
Assess current task execution state using section §2 criteria. If not eligible → deny request with completion requirements. If eligible → proceed to context gathering.

### Step 2: Context Synthesis and Validation
Synthesize current task execution state by reviewing the Memory Logs you populated for task completion history, outcomes, and working environment insights.

### Step 3: Artifact Creation
Create Implementation Agent Handover File and Handover Prompt using templates in section §4. Follow file organization in section §5.

### Step 4: User Review and Finalization
Present artifacts to User for review, accept modifications, confirm completeness before User executes handover procedure.

#### Handover Procedure Overview
After confirming completeness, User will open a new chat session, initialize a new Implementation Agent instance and paste the Handover Prompt. This chat session will replace you as the Implementation Agent for this APM session.

---

## 4 Implementation Agent Handover Artifacts
Create Handover Artifacts following these templates:

### Implementation Agent Handover Prompt Template
```markdown
# APM Implementation Agent Handover - [Agent Type]
You are taking over as [Agent_Type] for ongoing task execution from [Outgoing Agent ID].

## Context Integration Protocol
1. **Read Memory Log Guide** ([guides/Memory_Log_Guide.md]) to understand Memory Log structure and Implementation Agent logging responsibilities
2. **Read outgoing agent's Memory Logs** (chronological order) ([path/to/memory-logs]) to understand task execution history, outcomes, and blockers
3. **State your understanding of your logging responsibilities** based on the guide and **await User confirmation** to proceed to the next step
4. **Read Handover File** ([path/Agent_Type_Handover_File_X.md]) for active memory context of the outgoing agent not captured in Memory Logs

## Cross-Reference Validation
Compare Handover File active memory against your Memory Logs for task execution outcomes and working environment context. Note contradictions for User clarification.

## Current Task Context
- **Last Completed Task:** [Task ID and completion status]
- **Working Environment:** [Brief description from active memory]
- **User Preferences:** [Key preferences from active memory]

## User Verification Protocol
After context synthesis: ask 1-2 assurance questions about task execution history accuracy, if contradictions found ask specific clarification questions, await explicit User confirmation before proceeding.

**Immediate Next Action:** [Current status - awaiting assignment]

Acknowledge receipt and begin context integration protocol immediately.
```

### Implementation Agent Handover File Format
```yaml
---
agent_type: Implementation
agent_id: Agent_[Name]_[X]
handover_number: [X]
last_completed_task: [Task ID]
---
```
```markdown
# Implementation Agent Handover File - [Agent Type]

## Active Memory Context
**User Preferences:** [feedback patterns, constraints, development preferences]
**Working Insights:** [Discoveries about codebase, workflow patterns, recurring issues, effective approaches - all relative to Task Assignments received]

## Task Execution Context
**Working Environment:** [File locations, codebase patterns, important code snippets, development environment setup, key directories/files/modules]
**Issues Identified:** [resolved/persistant issues, persistant bugs, any ad-hoc delegations,]

## Current Context
**Recent User Directives:** [Unlogged user instructions, clarifications, task modifications not captured in Memory Logs]
**Working State:** [Current file locations, environment setup, tools configuration]
**Task Execution Insights:** [Patterns discovered during task execution, effective approaches, issues to avoid]

## Working Notes
**Development Patterns:** [Effective coding approaches, user-preferred solutions, successful strategies]
**Environment Setup:** [Key file locations, configuration preferences, tool usage patterns]
**User Interaction:** [Effective communication patterns, clarification approaches, feedback integration]
```

---

## 5 File Organization and Naming
Store Implementation Agent Handover Files in `Memory/Handovers/[Agent_Name]_Handovers/` (Dynamic Memory) or `project-root/Handovers/[Agent_Name]_Handovers/` (Simple Memory). Use naming: `[Agent_Name]_Handover_File_[Number].md`. Handover Prompts are created as markdown code blocks, not stored as files.

---

**End of Guide**