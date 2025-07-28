# APM v0.4 - Implementation Plan Review Guide
This guide defines how Setup Agents review the Implementation Plan to detect and fix critical task quality issues before enhancement. This guide uses phase-by-phase review cycles with task-level error detection and systematic fixing protocols.

---

## 1. Review Protocol Overview

### Review Purpose
Conduct systematic review of simple Implementation Plan to identify and fix critical task quality issues that would impair Implementation Agent success:
- Task packing violations (multiple distinct activities in one task)
- Classification errors (wrong single-step vs multi-step designation)
- Step quality issues (poor breakpoints, template matching patterns)
- Task execution scope errors (external platform assumptions)
- User requirement compliance failures (Context Synthesis requirements missing from tasks)
- Phase delivery gaps (phases don't address user project needs)

### Review Methodology
**Phase-by-Phase Systematic Review:** Complete review of one phase before proceeding to next phase using error detection → cataloging → fixing workflow.

**Error Detection Workflow:**
1. **Task-by-Task Analysis**: Examine each task individually for all error categories
2. **Error Cataloging**: Document all detected errors before attempting fixes
3. **Fix Proposal**: Present proposed solutions for all catalogued errors in chat
4. **User Collaboration**: Present decision points requiring user input
5. **Fix Application**: Apply approved fixes systematically to Implementation Plan file
6. **Phase Validation**: Verify phase integrity after fixes before proceeding

**Mandatory Progression Gates:** Cannot proceed to next phase without completing entire error detection and fixing cycle for current phase.

### Error Classification for Fix Approach
**Critical Auto-Fix Issues** (Agent applies immediately):
- Clear task packing violations
- Obvious classification errors
- Template matching patterns
- Execution scope violations
- Explicitly missing user requirements

**User Collaboration Issues** (Require user input):
- Borderline task boundary decisions
- Agent workload distribution preferences
- Phase structure optimization questions
- Task granularity judgment calls
- Ambiguous requirement interpretations
- Quality vs efficiency tradeoffs

---

## 2. Error Categories & Detection Criteria

### 2.1. Task Packing Violations
**Definition**: Single task containing multiple distinct activities that could be completed independently.

**Detection Criteria:**
- Task involves multiple unrelated technical domains
- Task description uses "and" to connect disparate activities
- Task could be naturally divided into separate deliverables
- Multiple agents could work on different parts simultaneously

**Examples of Task Packing:**
- "Implement authentication AND set up database schema"
- "Create UI components AND configure deployment pipeline"
- "Write documentation AND implement API endpoints"

### 2.2. Classification Errors
**Definition**: Incorrect single-step vs multi-step designation based on actual workflow requirements.

**Single-Step Misclassification Signs:**
- Task involves sequential technical phases requiring separate validation
- Task requires user coordination or feedback during execution
- Task has natural breakpoints where progress should be confirmed
- Task combines research/planning with implementation

**Multi-Step Misclassification Signs:**
- Task is cohesive single activity without internal dependencies
- Steps are artificially divided without genuine workflow breakpoints
- All "steps" could be completed as one focused effort
- Steps don't require user confirmation between them

### 2.3. Step Quality Issues
**Definition**: Multi-step tasks with poor step definition or template matching patterns.

**Step Quality Problems:**
- **Template Matching**: Rigid step count patterns (all tasks have 3, 4, or 5 steps)
- **Poor Breakpoints**: Steps don't align with natural workflow progression
- **Micro-Management**: Steps are too granular (individual commands)
- **Macro-Steps**: Steps are too broad (complete phases)
- **No Progression**: Steps don't build meaningfully toward task completion

### 2.4. User Requirement Compliance Failures
**Definition**: Tasks missing explicit integration of emphasized user requirements from Context Synthesis.

**Compliance Check:**
- Process requirements (workflows, quality standards, validation approaches)
- Technical constraints (tools, platforms, implementation preferences)
- Coordination requirements (review processes, approval gates)
- Quality standards (acceptance criteria, validation requirements)

### 2.5. Phase Delivery Gaps
**Definition**: Phases that don't adequately address user project needs or logical progression.

**Phase Assessment:**
- Does phase deliver meaningful value toward project completion?
- Are phase boundaries logical and support natural workflow progression?
- Do phase tasks collectively address user requirements for this stage?

### 2.6. Task Execution Scope Errors
**Definition**: Tasks incorrectly scoped for Implementation Agent capabilities vs User coordination requirements.

**Implementation Agent Capabilities:**
- Actions within IDE environment (code, files, terminal, analysis tools)
- Same tools and environment access as Setup Agent
- No access to external platforms, dashboards, or User-specific accounts

**Execution Scope Error Types:**
- **External Platform Assumption**: Task assumes agent can access cloud dashboards, deployment platforms, or external services
- **User Account Control Violation**: Task requires authentication/permissions agents cannot access
- **Platform UI Interaction**: Task involves web interfaces, settings panels, or manual configuration
- **Mixed Execution Confusion**: Task combines agent-executable actions with external platform actions without proper separation
- **Wrong Language Usage**: Task uses execution verbs ("configure," "deploy," "setup") for external actions instead of guidance language ("guide," "provide instructions," "prepare documentation")

**Proper Execution Scope Patterns:**
- **Agent-Executable**: Direct implementation within IDE environment
- **User-Guided**: Agent provides instructions/documentation for User actions
- **Mixed (Properly Separated)**: Agent preparation tasks + separate User guidance tasks

---

## 3. Phase Review Cycle Execution

### 3.1. Phase Content Analysis
**Objective**: Systematically analyze phase structure and task quality.

#### Phase Delivery Validation
- **Phase Purpose Check**: Does this phase deliver clear value toward project completion?
- **User Requirement Coverage**: Do phase tasks address relevant user requirements from Context Synthesis?
- **Phase Boundary Logic**: Are phase boundaries appropriate for workflow progression?
- **Task Completeness**: Are all necessary tasks included for phase objectives?

#### Task Inventory and Overview
- **Task Count**: Document total tasks in current phase
- **Agent Distribution**: Note agent assignments and workload within phase
- **Dependency Structure**: Review intra-phase dependencies for logic
- **Execution Pattern Distribution**: Count single-step vs multi-step tasks

### 3.2. Task-by-Task Error Detection
**Objective**: Examine each task individually for all error categories before proposing fixes.

#### Systematic Task Analysis Process
**For each task in current phase, analyze in this order:**

1. **Task Packing Assessment**:
   - Does task contain multiple distinct activities?
   - Could task be naturally divided into separate deliverables?
   - Are there multiple unrelated technical domains involved?

2. **Classification Validation**:
   - Does current single-step/multi-step designation match workflow reality?
   - Are there genuine sequential dependencies requiring user confirmation?
   - Is task cohesive single activity or involves distinct phases?

3. **Step Quality Review** (Multi-step tasks only):
   - Do steps represent natural workflow breakpoints?
   - Is step count based on genuine dependencies vs template patterns?
   - Are steps appropriately granular and progressive?

4. **User Requirement Compliance**:
   - Are emphasized Context Synthesis requirements explicit in task specifications?
   - Do process requirements appear as concrete task components?
   - Are quality standards integrated as task objectives or validation criteria?

5. **Execution Scope Validation**:
   - Does task assume Implementation Agent can access external platforms or services?
   - Are User-specific account actions properly identified for User coordination?
   - Is task language appropriate (execution vs guidance verbs)?
   - Are mixed execution tasks properly separated into agent + user components?

#### Error Documentation Protocol
**Document all detected errors before proposing fixes:**
- **Task ID**: Reference specific task with issue
- **Error Category**: Classification from Section 2
- **Error Description**: Specific problem identified
- **Impact Assessment**: How error would affect Implementation Agent execution

### 3.3. Error Cataloging and Fix Proposal
**Objective**: Present comprehensive error analysis and proposed solutions before applying fixes.

#### Error Summary Presentation
Present **in chat** complete error catalog for current phase:
- **Total Errors Detected**: Count by category
- **Critical Issues**: Errors that would block Implementation Agent success
- **Optimization Opportunities**: Areas for improvement
- **Pattern Analysis**: Recurring issues across multiple tasks

#### Fix Proposal Protocol
**For each detected error, propose specific fix:**
- **Task Packing**: Propose task division with logical boundaries
- **Classification Error**: Propose correct classification with rationale
- **Step Quality Issue**: Propose improved step breakdown with natural progression
- **User Requirement Gap**: Propose explicit requirement integration
- **Execution Scope Error**: Propose proper agent vs user action separation

#### Fix Validation
- **Dependency Impact**: How fixes affect task dependencies
- **Agent Assignment Impact**: How fixes affect workload distribution
- **Phase Integrity**: How fixes maintain phase coherence

#### User Collaboration Decision Points
**For issues requiring user input, present options with rationale:**

**Format for User Collaboration Items:**
- **Issue Description**: Specific decision needed
- **Options**: 2-3 potential approaches with pros/cons
- **Recommendation**: Agent's suggested approach with reasoning
- **Impact**: How decision affects overall plan structure

**Common Collaboration Categories:**
- **Task Boundary Decisions**: "Should this complex task be split into 2-3 separate tasks or remain as multi-step?"
- **Agent Workload Questions**: "Agent_X has 6 tasks while Agent_Y has 3 - redistribute or acceptable?"
- **Phase Structure Options**: "This phase could be split into setup + implementation phases - preference?"
- **Granularity Preferences**: "This task could be more granular (4 tasks) or less granular (2 tasks) - which approach?"

### 3.4. Systematic Fix Application
**Objective**: Apply approved fixes systematically to Implementation Plan file.

#### Collaboration Resolution Protocol
**Before applying fixes:**
1. **Auto-Fix Items**: Apply critical fixes immediately as proposed
2. **User Collaboration Items**: Present decision points to User and await responses
3. **Iterative Refinement**: Incorporate user decisions into fix application
4. **Final Validation**: Confirm all decisions (auto + collaborative) before file modification

#### Fix Application Process
1. **Fix Prioritization**: Apply fixes in logical order to minimize cascading changes
2. **File Modification**: Update Implementation Plan with approved fixes
3. **Dependency Adjustment**: Update affected dependencies after task changes
4. **Agent Reassignment**: Adjust agent assignments if task division affects workload

#### Cascading Error Prevention
After applying fixes:
- **Dependency Validation**: Verify all dependencies remain valid
- **Phase Coherence Check**: Ensure phase maintains logical structure
- **Cross-Phase Impact**: Note any effects on other phases

### 3.5. Phase Completion Validation
**Objective**: Verify phase integrity after fixes before proceeding to next phase.

#### Post-Fix Phase Assessment
- **Error Resolution Confirmation**: Verify all detected errors have been addressed
- **Phase Quality Validation**: Confirm phase delivers appropriate value and progression
- **Task Quality Standard**: Verify all tasks meet Implementation Agent execution requirements
- **User Requirement Integration**: Confirm Context Synthesis requirements properly integrated

#### Progression Gate Requirements
**Cannot proceed to next phase without:**
- All detected errors resolved or explicitly documented if unfixable
- Phase maintains logical coherence after fixes
- Task quality meets Implementation Agent execution standards
- User requirement integration verified

**Mandatory Completion Confirmation**: State explicit completion of systematic review for current phase.

---

## 4. Final Plan Validation

### 4.1. Holistic Plan Assessment
**After completing review for all phases:**

#### Cross-Phase Validation
- **Phase Progression Logic**: Verify logical flow between phases
- **Dependency Integrity**: Confirm all cross-phase dependencies remain valid
- **Agent Workload Balance**: Assess final agent distribution after fixes
- **User Requirement Coverage**: Verify complete Context Synthesis requirement integration

#### Template Matching Detection
- **Pattern Analysis**: Review task formats for rigid patterns across phases
- **Step Count Variation**: Verify natural variation in multi-step task complexity
- **Classification Distribution**: Ensure realistic single-step vs multi-step balance

### 4.2. Review Completion Summary
**Document comprehensive review outcomes:**

#### Changes Applied Summary
- **Tasks Modified**: List all tasks changed with modification type
- **New Tasks Created**: Document any task divisions or additions
- **Classification Changes**: Note any single-step ↔ multi-step conversions
- **Agent Reassignments**: Document any workload redistribution

#### Quality Improvements Achieved
- **Task Packing Resolution**: Number of overpacked tasks divided
- **Classification Corrections**: Number of misclassified tasks fixed
- **Step Quality Enhancements**: Number of multi-step tasks improved
- **Execution Scope Corrections**: Number of scope violations fixed
- **User Requirement Integration**: Verification of Context Synthesis requirement coverage

#### Final Plan Quality Assessment
- **Implementation Agent Readiness**: Confirm plan supports Implementation Agent success
- **User Requirement Compliance**: Verify comprehensive requirement integration
- **Execution Feasibility**: Validate task breakdown supports manageable execution scope

**Review Completion Confirmation**: Present refined Implementation Plan for user approval before proceeding to Enhancement phase.

---

**End of Guide**