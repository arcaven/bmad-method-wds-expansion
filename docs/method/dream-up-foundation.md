# Dream Up: Foundation Architecture

**Version:** 0.1.0 (Foundation)
**Status:** Design Phase
**Created:** 2026-02-11

---

## Overview

**Dream Up** is a three-tier engagement system that allows agents to generate quality output through self-review against WDS standards and tutorials, with varying levels of user involvement.

---

## Three Engagement Modes

### 1. Workshop Mode (Facilitated Discovery)
- Agent facilitates workshop to draw out user's best ideas
- Man-in-the-loop: Human actively involved, agent guides discovery
- Agent asks strategic questions that make user "go deep and really question themselves"
- Full back-and-forth dialog
- **Current WDS default**

### 2. Suggest Mode (Guided Review)
- Agent generates content
- Agent reviews against standards
- Agent shows iteration + rationale
- **User approves/adjusts each step**
- User can provide feedback to guide refinement

### 3. Dream Mode (Autonomous with Oversight)
- Agent generates content
- Agent reviews against standards using self-dialog
- Agent refines until quality threshold met
- **User can observe and interrupt at any time**
- Final output presented for approval

---

## Core Architecture

### Five-Layer System

```
┌─────────────────────────────────────────┐
│ Layer 1: Learn WDS Form (Static)        │
│ Agent learns methodology from tutorials │
│ Loaded once at start                    │
└─────────────────────────────────────────┘
              ↓
┌─────────────────────────────────────────┐
│ Layer 2: Project Context (Cumulative)   │
│ Product Brief → +Business Goals          │
│ → +Target Groups → +Driving Forces       │
│ Grows with each step completed          │
└─────────────────────────────────────────┘
              ↓
┌─────────────────────────────────────────┐
│ Layer 3: Domain Research (Per Step)     │
│ WebSearch for industry insights          │
│ User reviews, forums, competitor data    │
└─────────────────────────────────────────┘
              ↓
┌─────────────────────────────────────────┐
│ Layer 4: Generate Next Artifact         │
│ Apply Form + Use Context + Research      │
└─────────────────────────────────────────┘
              ↓
┌─────────────────────────────────────────┐
│ Layer 5: Self-Review Against Standards  │
│ Check quality → Refine → Add to Layer 2 │
└─────────────────────────────────────────┘
              ↓ (repeat for next step)
```

### Three Knowledge Sources

**1. WDS Learning Materials (FORM)**
- Methodology, structure, quality standards
- How to build artifacts correctly
- Agent becomes WDS expert

**2. Product Brief (SUBSTANCE)**
- Business context, users, goals, constraints
- Strategic direction
- User provides domain substance

**3. Online Research (DOMAIN INSIGHTS)**
- Industry patterns, user behavior
- Competitor analysis, reviews, forums
- Agent develops domain expertise

---

## Layer 1: Learn WDS Form

**Purpose:** Agent becomes WDS methodology expert by learning from tutorials and standards.

**Loaded:** Once at workflow start (static)

### What Agent Learns

**For Phase 2 (Trigger Mapping):**
- `docs/method/phase-2-trigger-mapping-guide.md` - Complete methodology
- `docs/quick-start/02-trigger-mapping.md` - Quick reference
- `src/data/agent-guides/saga/trigger-mapping.md` - Agent-specific guide
- `docs/models/impact-effect-mapping.md` - Foundational model
- `docs/method/dream-up-rubric-phase-2.md` - Quality rubric

**Agent Internalizes:**
- How to structure Trigger Map artifacts
- What makes quality vs poor output
- Common mistakes to avoid
- Best practices to follow
- Self-review process

**Documents in Agent Dialog:**
```markdown
## Layer 1: WDS Form Learned

### Resources Loaded
- [List of guides/tutorials]

### Key Learnings
- Structure: [What sections, how organized]
- Quality criteria: [What defines good output]
- Common mistakes: [What to avoid]
- Best practices: [What to aspire to]
```

---

## Layer 2: Project Context (Cumulative)

**Purpose:** Extract business substance from prior phases, grows with each step.

**Initial Load:** Product Brief (Phase 1)

**Cumulative Growth:**
```
Start: Product Brief
  ↓
After Business Goals: Product Brief + Business Goals
  ↓
After Target Groups: Product Brief + Business Goals + Target Groups
  ↓
After Driving Forces: All above + Driving Forces
  ↓
After Prioritization: All above + Prioritization
```

### Phase 1 Sources

**From Product Brief:**
- Business context (what, who, why)
- User archetypes mentioned
- Success criteria
- Constraints (technical, business, timeline)
- Tone and personality direction

**From Companion Docs:**
- Content & Language: Voice, tone, keywords
- Platform Requirements: Technical boundaries, integrations
- Visual Direction: Style, mood, aesthetic

### Extraction Process

1. **Initial load** from Product Brief artifacts
2. **Summarize key insights:**
   ```markdown
   ## Layer 2: Project Context (Initial)

   ### Business Context
   - [Key business facts]

   ### Users
   - [Archetypes mentioned]

   ### Constraints
   - [Technical, business, timeline]

   ### Strategic Direction
   - [Goals, positioning]
   ```
3. **After each step:** Add completed artifact to Layer 2
4. **Next step uses:** ALL accumulated context

---

## Layer 3: Domain Research

**Purpose:** Agent develops domain expertise through online research.

**Executed:** Per step, as needed for current artifact

### Research Sources

- Industry insights and best practices
- Competitor analysis
- User reviews and forums
- Behavioral patterns
- Market data

### Research Process

**For each step:**

1. **Identify research questions**
   - Example: "What drives customers to rural car mechanics?"
   - Example: "Northern Öland tourism caravan statistics"

2. **Execute WebSearch queries**
   - Look for user voices, forums, review sites
   - Find industry patterns and standards

3. **Synthesize findings**
   ```markdown
   ## Layer 3: Domain Research - [Step Name]

   ### Research Questions
   - [Question 1]
   - [Question 2]

   ### Findings
   - [Key insight 1 with source]
   - [Key insight 2 with source]

   ### Implications
   - [How this informs generation]
   ```

---

## Layer 4: Generate Next Artifact

**Purpose:** Synthesize all three sources into quality output.

**Input Sources:**
- Layer 1: WDS Form (how to structure)
- Layer 2: Project Context (business substance, ALL prior artifacts)
- Layer 3: Domain Research (industry insights)

**Generation Process:**

1. **Apply WDS structure** from Layer 1
2. **Use business context** from Layer 2 (cumulative)
3. **Enhance with insights** from Layer 3
4. **Create this step's artifact**

---

## Layer 5: Self-Review Against Standards

**Purpose:** Check quality, identify gaps, refine iteratively.

### The Self-Dialog Process

#### Step 1: Initial Generation
Agent generates first draft of content.

#### Step 2: Self-Review Against Standards
Agent evaluates its own work:

```markdown
## Self-Review: Iteration 1

### Completeness Check
- [✅/❌] Contains required sections
- [✅/❌] Sufficient depth
- [✅/❌] Actionable for next phase

### Quality Check Against Standards
1. **[Criterion from standards]**
   - ✅ Met: [Evidence]
   - ❌ Gap: [What's missing]

2. **[Another criterion]**
   - ✅ Met: [Evidence]
   - ❌ Gap: [What's missing]

### Common Mistakes Check
- [✅/❌] Avoided mistake X
- [✅/❌] Avoided mistake Y

### Best Practices Check
- [✅/❌] Following practice A
- [✅/❌] Following practice B

### Overall Assessment
- **Quality Score:** [X/10]
- **Gaps Identified:** [List]
- **Refinement Needed:** [Yes/No]
```

#### Step 3: Refinement (if needed)
If gaps identified, agent refines:

```markdown
## Refinement Plan: Iteration 2

### Addressing Gap 1: [Gap description]
**Action:** [What will be changed]
**Rationale:** [Why this addresses the gap]

### Addressing Gap 2: [Gap description]
**Action:** [What will be changed]
**Rationale:** [Why this addresses the gap]
```

Then generates Iteration 2 and repeats self-review.

#### Step 4: Quality Threshold Met
When self-review shows all criteria met:

```markdown
## Self-Review: Iteration N - COMPLETE

### All Criteria Met ✅
- Completeness: 100%
- Quality standards: All green
- No common mistakes
- Best practices followed

### Ready for User Review
**Confidence:** High
**Recommendation:** Present to user for approval
```

---

## Engagement Mode Differences

### Workshop Mode (Current WDS)
- **User involvement:** Continuous, man-in-the-loop
- **Self-dialog:** None (agent facilitates workshop with user)
- **Quality control:** Through strategic questioning that draws out user's best ideas
- **Best for:** Discovery, strategic decisions, learning the method, first time through

### Suggest Mode
- **User involvement:** Checkpoint approval
- **Self-dialog:** Visible after each iteration
- **Quality control:** User review of self-assessment
- **Best for:** Guided work, learning the method

**Format:**
```markdown
### Iteration 1
**Generated:** [Content]

**Self-Review:**
- ✅ Strengths: [...]
- ❌ Gaps: [...]

**Refinement:** [Updated content]

👉 **User Checkpoint:** [Continue] [Adjust] [Stop]
```

### Dream Mode
- **User involvement:** Observation + interrupt capability
- **Self-dialog:** Fully autonomous, visible
- **Quality control:** Standards-based self-review
- **Best for:** Routine tasks, clear requirements, established patterns

**Format:**
```markdown
## Dream Mode: [Task Name]

🔄 Iteration 1 → Self-Review → Gaps found → Refining...
🔄 Iteration 2 → Self-Review → Gaps found → Refining...
🔄 Iteration 3 → Self-Review → All criteria met ✅

**Output Ready for Review**

[Content]

💬 User can type "stop" at any time to interrupt
```

---

## Quality Thresholds

### Minimum Criteria (Must Meet All)
- [ ] All required sections present
- [ ] No common mistakes detected
- [ ] Depth sufficient for next phase
- [ ] Actionable (concrete, not vague)

### Excellence Criteria (Nice to Have)
- [ ] Best practices followed
- [ ] Rich examples/specificity
- [ ] Insights beyond obvious
- [ ] Strong connections to business goals

### Iteration Limits
- **Max iterations:** 5
- **If not meeting criteria after 5:** Switch to Workshop Mode (ask user questions)

---

## Agent Dialog Structure for Dream Up

When Dream Up is invoked, create agent dialog:

```markdown
# Agent Dialog: Dream Up - [Task Name]

**Created:** [Date Time]
**Mode:** [Workshop/Suggest/Dream]
**Phase:** [2/3/4/etc.]
**Project:** [Project name]

---

## Context Loaded

### From Phase 1
- [Summary of business context]
- [Summary of users]
- [Summary of constraints]

### Standards Loaded
- [List of guides/tutorials referenced]
- [Quality criteria extracted]

---

## Generation Log

### Iteration 1
**Generated:** [Summary]
**Self-Review:** [Assessment]
**Outcome:** [Refine/Complete]

### Iteration 2 (if needed)
**Refined:** [What changed]
**Self-Review:** [Assessment]
**Outcome:** [Refine/Complete]

---

## Final Output

[Link to generated artifact]

**Quality Score:** [X/10]
**User Approved:** [Yes/No]
**Notes:** [Any user feedback]
```

---

## Implementation Plan

### Phase 1: Foundation (Current Step)
- [x] Design architecture
- [ ] Create template agent dialogs
- [ ] Document standards extraction process
- [ ] Define quality rubrics by phase

### Phase 2: Prototype (Suggest Mode)
- [ ] Test on Källa Phase 2 (Trigger Mapping)
- [ ] Validate self-review process
- [ ] Refine quality criteria
- [ ] User feedback on visibility/control

### Phase 3: Dream Mode
- [ ] Build fully autonomous loop
- [ ] Add interrupt capability
- [ ] Test with multiple projects
- [ ] Measure quality vs. Workshop Mode

### Phase 4: Integration
- [ ] Integrate into all Phase 2+ workflows
- [ ] User choice: Workshop/Suggest/Dream at workflow start
- [ ] Agent can recommend mode based on context
- [ ] Documentation and training

---

## Success Metrics

**Quality:**
- Generated output meets WDS standards 95%+ of time
- User approval rate > 90%
- Fewer than 3 iterations average

**Efficiency:**
- Suggest Mode: 50% time reduction vs. Workshop
- Dream Mode: 75% time reduction vs. Workshop

**Learning:**
- Users understand WDS methodology better through visible self-dialog
- Self-review serves as tutorial/education

---

## Next Steps

1. **Create Phase 2 (Trigger Mapping) quality rubric**
2. **Test Suggest Mode on Källa project**
3. **Refine based on real-world use**
4. **Expand to other phases**

---

*Dream Up enables high-quality, standards-aligned output with flexible user involvement.*
