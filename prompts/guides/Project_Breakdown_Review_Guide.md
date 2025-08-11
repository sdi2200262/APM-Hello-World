# APM v0.4 - Project Breakdown Review Guide
This guide defines how Setup Agents conduct targeted, user-selected review of Implementation Plans to detect and fix critical task quality issues before enhancement. Using fresh context from Implementation Plan creation, agents propose specific areas for systematic review and let users choose which sections receive detailed analysis.

---

## 1. Review Protocol Overview

### Review Purpose
Conduct systematic review on user-selected portions of the Implementation Plan to identify and fix critical task quality issues:
- Task packing violations (multiple distinct activities in one task)
- Classification errors (wrong single-step vs multi-step designation)
- Template matching patterns (rigid formatting across tasks)
- User requirement compliance failures (Context Synthesis requirements missing)
- Task execution scope errors (external platform assumptions)

### Context-Driven Review Methodology
**Agent Proposal → User Selection → Targeted Systematic Review → Comprehensive Fixing**

**Review Workflow:**
1. **Intelligent Proposal**: Agent analyzes fresh Implementation Plan context to recommend review areas
2. **User Selection**: User chooses which tasks/phases receive systematic review
3. **Systematic Analysis**: Apply full testing methodology only to selected areas
4. **Comprehensive Fixing**: Fix all issues in selected areas and apply patterns to unreviewed areas
5. **Final User Review**: Present complete updated plan for approval

**Efficiency**: Full systematic review power applied only where most valuable

---

## 2. Intelligent Review Area Proposal

### 2.1. Context Analysis for Proposal Generation
**Leverage fresh Implementation Plan creation context to identify high-value review targets:**

**Immediate Context Awareness:**
- **Complex Multi-Step Tasks**: Tasks with 6+ steps that might need splitting
- **Technology Span**: Tasks covering multiple domains or skill areas
- **Critical Path Items**: Tasks with multiple dependencies or cross-agent handoffs
- **User Requirement Areas**: Sections containing emphasized Context Synthesis elements
- **External Integration Points**: Tasks involving deployment, configuration, or platform coordination

### 2.2. Proposal Categories
**Recommend review areas based on detected patterns:**

**High-Complexity Areas:**
- Phases with multiple 6+ step tasks
- Tasks spanning different technology domains
- Sections with dense cross-agent dependencies

**Critical Path Areas:**
- Tasks that block multiple other tasks
- Cross-agent handoff points
- External platform integration tasks

**User Requirement Areas:**
- Sections implementing emphasized Context Synthesis requirements
- Tasks involving user-specific preferences or constraints

**Pattern Concern Areas:**
- Groups of tasks with identical formatting
- Sections that might have template matching issues

### 2.3. Proposal Presentation Format
**Present clear, actionable recommendations to user:**

**Format Structure:**
```markdown
## Systematic Review Recommendations

Based on the Implementation Plan I just created, I recommend systematic review for:

**High-Complexity Areas:**
- **[Phase/Task ID]** ([complexity indicators: multi-step count, domain span, etc.])
- **[Phase/Task ID]** ([specific complexity reasoning])

**Critical Path Areas:**
- **[Phase/Task ID]** ([dependency description and impact])
- **[Phase/Task ID]** ([external coordination requirements])

**User Requirement Integration:**
- **[Phase/Task ID]** ([specific Context Synthesis requirements implemented])

**Pattern Concerns:**
- **[Task Range]** ([template matching or formatting issues identified])

**Recommendation:** Focus systematic review on [highest-value selections] for maximum impact.

**Your Choice:** Select any combination of the above recommendations, or specify other tasks/phases you'd like reviewed. I'll apply full systematic analysis only to your selected areas.
```

**Proposal Guidelines:**
- Limit recommendations to 4-6 items maximum for clear decision-making
- Provide specific reasoning for each recommendation
- Highlight 1-2 top priorities for user guidance
- Always offer user flexibility to modify selections

---

## 3. User Selection Process

### 3.1. Selection Options
**Flexible selection allowing user control:**

**Selection Formats User Can Choose:**
- **Full Phase Selection**: "Review [Phase X]" (all tasks in specified phase)
- **Multiple Phases**: "Review [Phases X and Y]" (multiple complete phases)
- **Individual Tasks**: "Review [Task X.Y] and [Task Z.A]" (specific task selections)
- **Task Ranges**: "Review [Tasks X.Y-X.Z]" (sequential task groups)
- **Mixed Combinations**: "Review [Phase X] and [Task Y.Z]" (phases plus individual tasks)
- **Exclusion Approach**: "Review everything except [Phase/Task identifiers]" (comprehensive minus exclusions)

**Additional Selection Capabilities:**
- User can add tasks not included in agent recommendations
- User can request focus on specific aspects (classification, packing, requirements integration)
- User can modify agent recommendations by adding or removing items

### 3.2. Selection Confirmation
**Clear confirmation of review scope before proceeding:**

**Confirmation Format:**
```markdown
**Selected for Systematic Review:**
- [Phase/Task selections with task counts]
- [Individual task selections]
- [Any special focus areas requested]

**Total:** [X] tasks receiving full systematic analysis
**Proceeding with systematic review of selected areas...**
```

**Confirmation Requirements:**
- List all selected phases and individual tasks
- Provide total task count for scope clarity
- Confirm any special focus areas or constraints
- Obtain explicit user approval before proceeding

---

## 4. Systematic Analysis (Selected Areas Only)

### 4.1. Full Testing Methodology
**Apply comprehensive testing to selected tasks only:**

For each selected task, conduct systematic analysis:

**Task [X.Y]: [Task Name] - Systematic Review**

1. **Task Scope Optimization Test**:
   - List distinct activities and evaluate independence
   - Assess granularity and combination opportunities
   - Evaluate step efficiency for multi-step tasks

2. **Classification Test**:
   - List workflow steps and validation needs
   - Assess workflow efficiency vs interruption costs

3. **Template Matching Test**:
   - Compare formatting to other tasks
   - Evaluate complexity-formatting alignment

4. **User Requirements Test**:
   - Identify applicable Context Synthesis requirements
   - Check integration into task specifications

5. **Execution Scope Test**:
   - Identify external dependencies and coordination needs
   - Categorize agent vs user capabilities

**Decision:** [Issue found/No issues] + brief reasoning
**Fix Applied:** [Specific changes made if issues found]

### 4.2. Issue Documentation
**Track all issues found in selected areas:**

**Documentation Format:**
```markdown
**Issues Found in Selected Areas:**
- [Task ID]: [Issue type] ([resolution applied])
- [Task ID]: [Issue type] ([resolution applied])
- [Task Range]: [Pattern issue] ([pattern fix applied])
```

**Documentation Requirements:**
- List each task with issues found during systematic review
- Specify issue type (packing violation, classification error, missing requirements, etc.)
- Document specific resolution applied
- Group similar issues for clarity

---

## 5. Comprehensive Fixing & Pattern Application

### 5.1. Selected Area Fixes
**Apply all identified fixes to selected tasks:**

- Fix packing violations through task splitting
- Correct classification errors
- Add missing user requirements
- Resolve template matching issues
- Clarify execution scope boundaries

### 5.2. Pattern Application to Unreviewed Areas
**Apply learned patterns to improve entire plan:**

**If Pattern Found in Selected Areas:**
- **Packing patterns**: Scan unreviewed areas for similar packing indicators
- **Classification patterns**: Check unreviewed tasks with similar characteristics
- **Template matching**: Vary formatting across unreviewed similar tasks
- **Missing requirements**: Add requirements to unreviewed tasks in similar domains

**Conservative Application:**
- Apply only clear, obvious patterns to unreviewed areas
- Avoid extensive changes to unreviewed sections
- Focus on applying lessons learned from systematic review

### 5.3. Comprehensive Plan Update
**Update entire Implementation Plan with all changes:**

1. **Apply systematic review fixes** to selected areas
2. **Apply pattern-based improvements** to unreviewed areas
3. **Maintain consistency** across entire plan
4. **Update task numbering** and dependencies as needed

---

## 6. Final User Review

### 6.1. Review Summary Presentation
**Clear summary of all changes made:**

**Summary Format:**
```markdown
## Review Complete - Summary of Changes

**Systematic Review Applied To:**
- [Phase/Task selections] - Found and fixed: [issue summary with counts]
- [Individual tasks] - Found and fixed: [specific issues]
- [Any areas with no issues found]

**Pattern-Based Improvements Applied:**
- [Description of patterns found and applied to unreviewed areas]
- [Count and type of improvements made based on systematic review findings]

**Total Changes:**
- [X] tasks split ([original] → [new task breakdown])
- [X] tasks reclassified ([classification changes made])
- [X] tasks enhanced with [type of enhancements]
- [X] tasks reformatted for [formatting improvements]

**Ready for Enhancement Phase**
```

**Summary Requirements:**
- Clearly distinguish between systematic review fixes and pattern-based improvements
- Provide specific counts and types of changes made
- List any task splits with before/after identification
- Confirm readiness for next phase

### 6.2. Final Approval Process
**User review and approval:**

1. **Present updated Implementation Plan** with all changes
2. **Highlight major modifications** for user attention
3. **Request explicit approval** to proceed to Enhancement phase
4. **Address any user concerns** or additional changes
5. **Confirm completion** when user approves

---

## 7. Integration with Enhancement Phase

### 7.1. Quality Handoff
**Ensure smooth transition to Enhancement:**

- **Systematic Review Documentation**: Note which areas received full review
- **Issue Resolution Confirmation**: Verify all identified issues are resolved
- **Pattern Application Documentation**: Record improvements applied to unreviewed areas
- **User Approval Confirmation**: Explicit approval for Enhancement phase

### 7.2. Enhancement Phase Notes
**Provide context for Setup Agent Enhancement:**

- Areas that received systematic review and are high-confidence
- Areas that received pattern-based improvements only
- Specific user requirements and preferences validated during review
- Any remaining user collaboration items for Enhancement phase

---

**End of Guide**