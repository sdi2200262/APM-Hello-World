# APM v0.4 - Project Decomposition Guide
This guide defines how Setup Agents transform Context Synthesis findings into structured, agent-assigned task breakdowns. Following systematic high-level-to-detail methodology, it prevents template matching through strategic workflow sequencing and chat-to-file output switching. The guide ensures task breakdown precision required for Implementation Agent success while minimizing Manager Agent coordination overhead.

## 1. Context Integration & Breakdown Overview

### 1.1. Retained Context Synthesis Insights
Project decomposition transforms Context Synthesis findings into structured task breakdown using **retained insights** from discovery phase. These insights provide concrete decision anchors:

- **Domain boundaries** → Create coherent agent assignments (see §2.1) 
- **Complexity flags** → Create appropriately granular tasks (see §4.1)
- **External dependencies** → Plan User guidance for actions outside IDE (see §4.1)
- **Investigation needs** → Plan Ad-Hoc delegation steps (see §4.2)
- **Workflow patterns** → Honor natural progression in dependencies (see §4.4)

### 1.2. Project Breakdown Sequence
The Setup Agent is to follow this systematic high-level-to-detail progression with mandatory progression gates:

1. **Domain Analysis** (§2) → Agent assignments **in chat**
2. **Phase Definition** (§3) → Phase sequence **in chat** 
3. **Phase Cycles** (§4) → Task breakdown **in chat** + documentation **in file**
4. **Final Review** (§5) → Agent splitting + cross-agent dependency marking **in file**
5. **Plan Approval** (§5.3) → User approval based on file + chat contents

**Progression Gates**: Each step must complete before proceeding to next step

### 1.3. Chat-to-File Workflow Pattern
Strategic context switching prevents pattern matching:

**Chat Operations**: Domain identification, phase sequence, task breakdown per phase, final review decisions
**File Operations**: Document each completed phase cycle, agent splitting updates, cross-agent dependency additions
**Context Breaks**: File writes interrupt continuous chat writing, providing fresh perspective for each subsequent phases thus avoiding pattern-matching

Simple file format (basic indentation, minimal structure - see §4.5) prevents template formation while preserving content for later formatting through `guides/Implementation_Plan _Format_Guide.md`

## 2. Domain Analysis & Agent Assignment

### 2.1. Domain Identification from Retained Context
Transform retained domain boundaries from Context Synthesis into logical work domains requiring different mental models and skill sets for Implementation Agent assignment:

#### Skill Area Separation
- Different expertise areas retained → Separate agents requiring distinct knowledge bases
- Different technical environments noted → Domain-specific agents for each technology stack
- Investigation versus execution needs identified → Research-focused versus implementation-focused agent separation

#### Mental Model Boundaries
- User-facing versus system-facing work patterns → Client-side versus server-side domain separation
- Creative versus analytical work streams → Content-oriented versus data-oriented domain boundaries
- Configuration versus development activities → Setup-focused versus feature-focused agent domains

#### Domain Coherence Criteria
Evaluate potential domains against coherence requirements for Implementation Agent success:

**Single Mental Model Requirement:**
- All tasks within domain require similar thinking approach and problem-solving methodology
- Domain scope maintains consistent technical knowledge and skill set requirements
- Task progression within domain follows natural workflow patterns without context or mental-model switching

**Natural Workflow Groupings:**
- Tasks within domain build upon each other logically with minimal external dependencies
- Domain boundaries align with retained workflow relationships from Context Synthesis
- Work progression within domain maintains context continuity for Implementation Agent execution

**Boundary Validation:**
- Domain separation minimizes coordination and context-integration overhead for Manager Agent
- Each domain delivers independent value while supporting overall project goals
- Domain scope prevents Implementation Agent confusion

### 2.2. Initial Implementation Agent Team Creation
Transform identified domains into initial Implementation Agent assignments:

#### Assignment Process
Present complete agent team with domain rationale:
- Create one Implementation Agent per identified logical domain from §2.1 analysis
- Assign descriptive agent identifiers reflecting domain scope: `Agent_<Domain>`
- Estimate likely cross-agent dependencies (see §5.2) and minimize through coherent domain boundaries
- Note that workload distribution review occurs later (see §5.1) and may require agent subdivision

#### First Chat Action
Upon reading the guide, immediately write **in chat** domain analysis and initial agent assignments before proceeding to phase definition (see §3). This establishes the implementation agent team foundation for subsequent task assignments.

## 3. Phase Sequence Definition  

### 3.1. Phase Identification from Retained Workflow Patterns
Transform retained workflow patterns from Context Synthesis into logical project progression structure:

#### Phase Structure Determination
Use retained scope and workflow patterns to determine appropriate phase organization:

**Complexity Pattern Analysis:**
- Layered complexity flagged → Hierarchical phases with progressive dependencies
- Sequential patterns retained → Linear phases following natural workflow progression  
- Concurrent work streams noted → Parallel phases organized by domain or component boundaries

**Start-to-Finish Logic:**
- Identify project initiation requirements from retained context
- Define continuity workflow maintaining momentum between phases
- Establish completion criteria and final deliverable boundaries
- Ensure natural project progression without forced dependencies

#### Phase Boundary Assessment
- Extensive research requirements identified → Dedicated research phases when investigation blocks subsequent work
- Testing and validation requirements identified → Separate validation phases or integrated checkpoints
- Retained bottlenecks and critical path items → Natural phase boundaries at project constraints
- Simple scope understanding → Linear task progression without phase organization

#### Phase Scope Criteria
Evaluate phase necessity and boundaries against project requirements:
- Each phase delivers independent value toward project completion
- Phase boundaries align with retained workflow relationships and natural checkpoints
- Phase organization reduces cross-agent coordination complexity
- Phase scope supports Implementation Agent context preservation within domains

### 3.2. Phase Progression Logic
Transformed defined project sequence in §3.1 into phased project structure:

#### Presentation Process
Present the full phase sequence with supporting rationale:
- List phases in execution order, providing justification based on retained workflow patterns: `Phase X: <Phase_Name>`
- Note phase dependencies and deliverable handoff points between phases
- Confirm that phase organization aligns with Context Synthesis insights and project requirements
- Ensure phase boundaries support natural workflow progression and minimize cross-phase coordination complexity
- Proceed to phase cycle execution (see §4) following the established sequence

#### Second Chat Action
After presenting agent team assignments (see §2.2), immediately write **in chat** phase sequence analysis before beginning phase cycles (see §4). This establishes project structure foundation for systematic task breakdown.

## 4. Phase Cycle Execution (Core Repetitive Process)
Sections 4.1-4.4 are chat operations for conceptual planning. Section 4.5 is file operation for documentation.

### 4.1. Task Identification & Scope Definition
Identify all tasks required for current phase completion using retained Context Synthesis insights:

#### Task Identification Process
- Transform phase objectives into focused tasks with single achievable units of work
- Separate activities that can be done independently into different tasks
- If objective contains multiple distinct activities, separate into individual tasks
- Let task complexity follow actual requirements, avoid forcing artificial consistency
- Each task should deliver independent value toward phase completion
- Use retained complexity flags to create appropriately granular task scope
- Apply retained domain boundaries to align tasks with agent assignments from §2.2

#### Execution Scope Determination
Determine whether tasks require Implementation Agent execution or User guidance:

**IDE Environment Capabilities:**
- Tasks specify direct Implementation Agent execution for actions within IDE environment
- Implementation Agents have access to same tools and environment as Setup Agent

**External Platform Action Identification:**
- Access boundaries → Does this require interfaces outside IDE environment?
- User account control → Does this require authentication/permissions agents cannot access?
- Platform-specific UI → Does this involve web interfaces, dashboards, or settings panels?
- User preference signals → Has user explicitly indicated they will handle configurations manually?

**Execution Approach:**
- External platform actions → Tasks specify Implementation Agent guidance for User actions
- Mixed execution tasks → Separate into agent-executable preparation + user-guided external actions
- Guidance language → Use "guide," "provide instructions," "prepare documentation" rather than "configure," "deploy," "setup"
- Retained investigation needs → Include dedicated research tasks or assign Research Ad-Hoc Agent

### 4.2. Execution Pattern Classification
Determine execution pattern for each identified task in §4.1 through systematic assessment:

#### Classification Questions
For each task, assess:
- Is the unit of work of this task a product of multiple sequential actions with "first this, then that" progression?
- Would the task execution benefit if there were internal user-approval checkpoints for clarity and reassurance or even guidance?
- Can Implementation Agent complete entire task in single focused exchange?
- Would task benefit from Ad-Hoc research as first initial step?

#### Pattern Assignment
- **Single-step**: No internal sequential dependencies, completable in one exchange
- **Multi-step**: Sequential internal dependencies requiring progressive User confirmation

#### Task Classification Presentation
Present **in chat** a list of all tasks: "Task X.Y: <Task_Name> - Agent_<Domain> - (single-step)" or "Task X.Y: <Task_Name> - Agent_<Domain> - (multi-step)"

### 4.3. Step Count Definition (Multi-step Tasks)
Define sequential steps for each multi-step task you identified in §4.2 based on actual workflow requirements:

#### Step Assessment Questions
For each multi-step task you identified and presented in §4.2:
- How many genuine "first this, then that" dependencies exist?
- Where do natural pause points for User confirmation occur?
- Are there points requiring User guidance or clarification?

#### Step Definition Process
- Base step count on actual workflow dependencies for unit of work completion, not predetermined patterns
- Each step builds upon previous step with clear advancement
- Use numbered list format with clear description of step content

#### Multi-step Task Presentation  
Present **in chat** all multi-step tasks with numbered list step breakdown

### 4.4. Dependency Assessment & Documentation
Identify task dependencies within current phase using retained workflow relationships:

#### Dependency Assessment
- Look for retained "must do A before B" patterns from Context Synthesis for current phase
- Identify genuine producer-consumer relationships between tasks you identified in §4.2
- Define dependencies based on real workflow requirements, not artificial ones
- Minimize unnecessary dependencies - only when work requires previous outputs
- Prefer assigning dependent tasks to same agent when possible

#### Dependency List Presentation
Present **in chat** complete dependency list using simple notation: "Task X.Y depends on Task Z.W output"

### 4.5. Phase Documentation Procedure
Document completed phase cycle in file format to provide context break and preserve structured progress:

#### File Creation Process
- **First phase cycle**: Create `Implementation_Plan.md` at workspace root with current phase content only
- **Subsequent phase cycles**: Append current phase content to existing file under previous phases
- **Single write operation**: Each phase cycle results in exactly one file write containing only current phase

#### Content Translation Format
Translate chat presentations from §4.1-4.4 into structured file format. Below follows an example with both task types and a task dependency:

```markdown
Phase <n>: <Phase_Name> - <All_Agents_Assigned>

Task <n.1>: <Task_Name> - Agent_<Domain>
1) step 1 details
2) step 2 details
...

Task <n.2>: <Task_Name> - Agent_<Domain> - Depends on Task <n.1> output
- description of single-step task content
```

## 5. Final Review & Cross-Agent Integration

### 5.1. Agent Workload Assessment & Sub-domain Splitting
Conduct first holistic review to assess agent workload distribution across entire plan. Overloaded Agents (8+ tasks) must be subdivided:

#### Agent Workload Assessment
- Count total tasks assigned to each agent across all completed phases
- Identify agents with 8+ task assignments requiring subdivision
- Review task distribution for logical coherence within agent domains

#### Sub-domain Splitting Process
For overloaded agents requiring subdivision:
- Analyze tasks within agent domain for logical sub-domain boundaries
- Create coherent sub-agents based on natural task groupings: Agent_<Domain>_<Subdomain>
- Redistribute tasks from overloaded agents to appropriate sub-agents based on logical boundaries
- Maintain domain coherence principles from §2.1 within sub-domain splits

#### Agent Reassignment File Update
Update `Implementation_Plan.md` with revised agent assignments:
- Modify all affected task entries with new sub-agent assignments
- Preserve exact task content, dependencies, and step definitions during reassignment
- Ensure file reflects **final agent assignment** before proceeding to §5.2

### 5.2. Cross-Agent Dependency Marking
Conduct second holistic review to identify and mark cross-agent dependencies using **final agent assignments** from §5.1:

#### Cross-Agent Dependency Identification
- Review entire plan with final agent assignments to identify cross-agent dependencies
- Mark dependencies as cross-agent only if producer and consumer tasks are assigned to different agents
- Tasks with "Depends on Task X.Y" are cross-agent dependent if Task X.Y's agent ≠ current task's agent
- Present all cross-agent dependencies identified **in chat** before proceeding to editing the file 

#### Dependency Notation File Update
Update `Implementation_Plan.md` with enhanced dependency notations:
- Add "by Agent Y" notation exclusively to cross-agent dependencies
- Preserve simple "Depends on Task X.Y output" format for same-agent dependencies

### 5.3. Conceptual Plan Presentation & User Approval
Present plan overview and request User approval based on complete file and chat context:

#### Overview Summary Presentation
Present **in chat** high-level plan statistics:
- Number of agents and domains
- Total phases with names and task count
- Total task count, and total task count per task type
- Cross-agent dependency count 

#### User Review & Approval Process
- Direct User to review complete structured plan in `Implementation_Plan.md`
- Reference detailed breakdown reasoning from previous chat exchanges (§2-§4)
- Handle modification requests through targeted revisions to affected plan sections
- Iterate until explicit User approval to proceed to Implementation Plan Creation Guide

**End of Guide**