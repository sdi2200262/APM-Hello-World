# APM v0.4 - Implementation Plan Review Guide
Systematic plan-wide agent validation followed by phase-by-phase analysis with mandatory immediate corrections. Complete validation of one phase before proceeding to the next. It references Project Decomposition Principles defined in the `guides/Implementation_Plan_Creation_Guide.md`.

---

## 1. Review Protocol Requirements

### Mandatory Execution Pattern
- **Plan-Wide Agent Validation First**: Must complete agent assignment corrections across entire plan before phase analysis begins
- **Sequential Phase Analysis**: Must complete entire 4-step analysis cycle for current phase before proceeding to next phase
- **Immediate Corrections**: All violations must be corrected at-the-spot during analysis, no deferral permitted
- **No Shortcuts**: Cannot skip steps, abbreviate analysis, or declare "no issues found" without systematic examination
- **One-Task-at-a-Time**: During task analysis, examine each task individually before proceeding to next task

### Context Reference Points
Before beginning systematic analysis, confirm access to retained Context Synthesis insights for validation anchors:
- User requirements and constraints
- Challenging areas and complexity flags
- Sequential workflow patterns
- Domain boundaries and skill separations

---

## 2. Plan-Wide Agent Assignment Validation
**Execute once before phase-by-phase analysis begins. Cannot proceed to Phase Review Cycle without completing agent validation.**

### Required Analysis Across Entire Plan
- **Domain Coherence**: Apply §2.6 Domain Separation Guidelines - verify same agent tasks require identical technical domain/mental model
- **Context Switching Detection**: Identify agents with fundamentally different skill sets across phases
- **Workload Distribution**: Count total tasks per agent - flag 8+ task overloads requiring subdomain splitting

### Agent Breaking Criteria
- **Different Domain**: Break by logical domain separation
- **Same Domain Overload**: Break by logical sub-domain separation (8+ tasks)

### IMMEDIATE CORRECTIONS REQUIRED
- Reassign domain coherence violations to appropriate agents
- Split overloaded agents by sub-domain boundaries
- Create new agent assignments for violations
- Update all task headers with corrected assignments
- Note new cross-agent coordination requirements

**PROGRESSION GATE**: All plan-wide agent assignment corrections must be applied before proceeding to Phase Review Cycle.

---

## 3. Phase Review Cycle (Repeat for Each Phase)
**MANDATORY COMPLETION**: Execute all 4 steps below for current phase. Cannot proceed to next phase without completing entire cycle.

### Step 1: Phase Content Analysis
**Objective**: Validate phase content against User intent and requirements.

#### Required Analysis
- **Task Inventory**: Count and list all tasks in current phase by ID and title
- **User Intent Matching**: Compare each task objective against retained User requirements from Context Synthesis
- **Scope Creep Detection**: Identify any tasks or subtasks implementing features not requested by User
- **Requirement Gap Analysis**: Identify missing tasks needed to fulfill User requirements for this phase domain
- **Necessity Validation**: Distinguish between User-requested work and technically-required supporting work
- **Intra-Phase Dependencies**: Apply §2.4 Dependency Assessment criteria to validate dependencies between tasks within current phase

**IMMEDIATE CORRECTIONS REQUIRED**:
- Remove tasks implementing unrequested features
- Add tasks for identified requirement gaps
- Modify task objectives to align with User intent
- Add missing intra-phase dependency declarations using "Depends on: Task X.Y Output" format
- Document and keep track of cascade effects from changes for Step 3 assessment

**PROGRESSION GATE**: Step 1 corrections must be applied to current phase before proceeding to Step 2.

### Step 2: Individual Task Analysis
**Objective**: Systematic validation of each task independently.

**MANDATORY ONE-AT-A-TIME EXECUTION**: Complete full analysis of Task N before analyzing Task N+1.

#### Required Analysis Per Task
**Task Scope Validation**:
- Apply §2.2 Unit of Work Decomposition to verify task contains one achievable objective
- Apply §2.2 Parallel Activity Detection test: "Can activities be completed by different agents on different days?"
- Apply §2.2 Completion Unit Assessment to verify independent value delivery

**Format Classification Validation**:
- Apply §2.3 Format Decision Logic independently for this task
- For multi-step tasks: Apply §2.3 Sequential Dependency Test - verify "Subtask B becomes impossible without Subtask A completion"
- For single-step tasks: Apply §2.3 Simultaneous Approach Test - verify all activities can be approached within one exchange
- Apply §2.3 Natural Step Count Principles - determine step count based on actual workflow dependencies, not patterns

**Task Quality Assessment**:
- **Objective Clarity**: Verify one-sentence goal requirement compliance
- **Output Specificity**: Confirm concrete deliverable specification
- **Guidance Usefulness**: Validate constraints and requirements provide Implementation Agent value
- **Subtask Quality**: Ensure subtasks provide clear, actionable guidance with sufficient detail for successful execution

**Execution Scope Validation**:
- Apply §2.5 External Platform Action Identification criteria
- Verify task language uses execution verbs only for IDE-accessible actions
- Confirm external platform actions use guidance language ("guide," "provide instructions," "prepare documentation")

**Ad-Hoc Delegation Assessment**:
- Apply §2.3 Research Delegation criteria for technologies requiring current documentation
- Apply §2.3 Debug Delegation criteria for complex technical challenges

**IMMEDIATE CORRECTIONS REQUIRED PER TASK**:
- Split packed tasks violating Unit of Work principles
- Correct format classification (single-step ↔ multi-step) based on workflow dependencies  
- Adjust step count to reflect actual sequential dependencies
- Enhance subtask descriptions for Implementation Agent success
- Refine objective/output/guidance for clarity and usefulness
- Add Ad-Hoc delegation steps where assessment criteria indicate necessity
- Correct execution scope language for external platform actions

**PROGRESSION GATE**: Complete corrections for current task before analyzing next task in phase. Complete all task corrections of current

### Step 3: Cross-Phase Impact Assessment
**Objective**: Document cascade effects from current phase corrections.

#### Required Documentation
- **Previous Phase Effects**: Note how current phase corrections affect dependencies from previous phases
- **Future Phase Effects**: Identify how current phase changes will impact subsequent phase requirements
- **Cross-Agent Coordination Changes**: Document new cross-agent dependencies created by Step 2 corrections
- **Dependency Chain Adjustments**: Note required updates to "Depends on: Task X.Y Output" declarations across phases

**IMMEDIATE DOCUMENTATION REQUIRED**:
- Record all cascade effects for progressive resolution during subsequent phase analysis
- Note dependency declaration updates needed for cross-phase coordination

**PROGRESSION GATE**: Step 3 documentation must be completed for current phase before proceeding to Step 4.

### Step 4: Phase Completion Validation
**Objective**: Verify current phase analysis completeness and correction application.

#### Required Verification
- **Content Verification**: Confirm all Step 1 corrections applied to current phase; explain rationale
- **Task Verification**: Confirm all Step 2 corrections applied to each task in current phase; explain rationale
- **Documentation Verification**: Confirm all Step 3 cascade effects documented
- **Guide Compliance**: Verify current phase now complies with all referenced guide principles (§2.1-§2.6)

**MANDATORY COMPLETION CONFIRMATION**: State explicit completion of systematic analysis for current phase.

**PROGRESSION GATE**: Cannot proceed to next phase without explicit completion confirmation of Steps 1-4 for current phase.

---

## 4. Final Cross-Phase Integration
**Execute only after completing 4-step cycle for ALL phases.**

**Cross-Phase Dependency Validation**:
- Apply Step 3 documented cascade effects to update cross-phase dependencies
- Add required "Depends on: Task X.Y Output" declarations identified during progressive analysis
- Verify all cross-agent coordination requirements are properly declared

**Overall Plan Coherence Assessment**:
- Confirm revised plan fulfills all retained User requirements from Context Synthesis
- Verify natural workflow progression across phases
- Validate agent workload distribution and domain coherence across entire plan

---

## 5. Review Completion Requirements
**Change Documentation Summary**:
- **Agent Assignment Changes**: Document all agent reassignments and workload redistributions from plan-wide validation
- **Content Changes**: List all tasks added, removed, or modified with rationale
- **Format Corrections**: Note all single-step/multi-step classification changes
- **Quality Enhancements**: Summarize objective/output/guidance refinements and subtask improvements
- **Dependency Additions**: List all "Depends on: Task X.Y Output" declarations added

**Guide Principle Reference**: For each category of changes, reference specific guide principles (§X.Y) that drove corrections.

**Systematic Validation Confirmation**: Confirm Implementation Plan now complies with all systematic validation criteria through plan-wide agent validation and phase-by-phase analysis.

**User Review Preparation**: Present revised Implementation Plan with systematic improvement summary for explicit User approval before proceeding to Memory Root Creation.

---

**End of Guide**