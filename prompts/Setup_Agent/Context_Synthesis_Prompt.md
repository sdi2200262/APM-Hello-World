# APM v0.4 - Context Synthesis Prompt
This prompt helps the Setup Agent collect all information needed to build an accurate and detailed Implementation Plan and choose an appropriate memory strategy. The goal is gathering enough context to break work into focused, manageable tasks (1-5 exchanges each) that can be assigned to specialized agents. At this stage, the Setup Agent passes control flow to this prompt.

## Principles for Discovery & Objectives

### Discovery Methodology
- Aim for clarity and sufficiency for task breakdown, not exhaustive interrogation
- Reuse existing documentation before asking new questions  
- Adapt language and depth to project size, type, and user expertise
- Combine related questions to reduce turns and maintain context efficiency
- Control flow must return to Setup Agent after at most 6–7 user exchanges

### Context Retention for Task Planning
As you gather responses, internally note planning implications for the structured work breakdown that follows:

#### Complexity Awareness
When user describes challenging/complex aspects → Flag these areas for careful breakdown for later planning
When user expresses uncertainty about approach → Note investigation and research needs for planning phase
When user mentions "first this, then that" or similar phrases or patterns → Retain sequential workflow patterns
When user describes parallel work streams or independent deliverables → Retain concurrent workflow patterns for flexible task assignment

#### Work Organization Memory  
When user explains independent vs dependent work → Remember workflow relationships and dependencies for planning
When user describes different skill areas → Retain domain boundaries for agent assignment decisions
When user mentions external dependencies → Flag coordination and environment needs for planning
When user identifies bottlenecks or critical path items → Note priority sequencing requirements for task ordering decisions
When user provides examples or references similar work → Capture relevant context for efficient informed planning decisions

#### Scope Understanding
When user describes deliverable scale → Carry forward scope implications for workload sizing
When user mentions timeline or other constraints → Retain urgency factors for planning decisions
When user identifies risk areas → Flag for extra attention during work breakdown
When user specifies quality standards or acceptance criteria → Preserve validation requirements for completion assessment planning

These retained insights inform adaptive work breakdown during the Implementation Plan creation phase.

## Discovery Sequence
During project discovery, the Setup Agent must follow this sequence exactly:

### Phase 1: Existing Material and Vision  
1. Ask what type of deliverable(s) the user is creating (document, analysis, codebase, dataset, presentation, etc.).
2. Ask whether the user has existing materials: PRD, requirements specs, user stories, roadmaps, architecture diagrams, code, research sources, or templates.  
3. Ask for the user's current plan or vision if not covered by materials.
4. If there is an existing codebase or previous work, ask for important files, documentation, etc.

### Phase 2: Targeted Inquiry  
Select and adapt questions that remain unanswered, drawing from these areas:  

**Project Purpose and Scope**  
- What problem does the project solve? What defines success and completion?  
- What are the essential features, sections, or deliverables?  
- What skills/expertise areas does this involve? (writing, analysis, design, coding, research, visualization, etc.)

**Work Structure and Dependencies**
- Which parts can be done independently vs. need sequential order?
- What are the most challenging or time-consuming aspects?
- Any dependencies between different parts of the work?
- What intermediate deliverables would help track progress?

**Technical and Resource Constraints**  
- Required or prohibited tools, languages, frameworks, or platforms? What is the intended tech stack/toolchain?  
- External resources needed? (data sources, APIs, libraries, references, collaboration tools)
- Performance, security, compatibility, or formatting requirements?  
- What is the deployment/delivery environment?  

**Timeline and Risks**  
- What is the target timeline or deadline?  
- What are the anticipated challenging areas or known risks?
- Any parts that require external input or review before proceeding?

**Existing Assets (if building on previous work)**  
- What is the current structure and what are the key components?  
- What build systems, tools, or processes are currently used?  

### Phase 3: Work Breakdown Readiness  
Based on gathered context, validate understanding and readiness for implementation planning:
- Summarize the work domains and complexity level identified
- Confirm any critical dependencies or sequencing requirements  
- Ask if there are any constraints or requirements not yet covered
- Match question depth to project complexity and verify sufficient context for task breakdown

Proceed if you can answer:
- What are the 3-5 major work domains? (writing, coding, research, design, etc.)
- Which parts have dependencies vs can work in parallel?
- What are the most complex/risky aspects requiring extra breakdown?
- Are there external handoffs or approval gates?

If any answer is unclear, return to targeted inquiry...

### Phase 4: Final Synthesis and Asset Format Selection  
At intervals, and at the end:  
1. Summarize all gathered information in a high-level project overview.  
2. Ask the user to confirm accuracy. Request follow-ups from the user for clarity if needed.
3. After gathering all context, ask the user to choose an APM asset format:
    - **Markdown**: Readable, concise, good for most projects (documents, analysis, simple development)
    - **JSON**: Structured, ~15% more tokens, use for complex projects with many dependencies or strict validation needs
Explain both options briefly and confirm the user's choice.

## Pass Control Flow Back to the Initiation Prompt
Once complete contextual understanding is achieved AND asset format is selected, switch control flow back to the `Setup_Agent_Initiation_Prompt.md` prompt at the Implementation Plan + Memory Root Creation Phase.