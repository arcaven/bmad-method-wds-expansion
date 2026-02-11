# Dream Up: Implementation Guide

**Version:** 0.1.0 (Foundation)
**Status:** Ready for testing
**Created:** 2026-02-11

---

## What is Dream Up?

**Dream Up** is a three-tier engagement system that allows WDS agents to generate quality output with varying levels of user involvement:

- **Workshop Mode:** Full collaboration (current WDS default)
- **Suggest Mode:** Agent generates → reviews → refines, user approves each iteration
- **Dream Mode:** Fully autonomous generation with visible self-dialog, user can observe/interrupt

All modes use **self-review against WDS standards** to ensure quality.

---

## System Architecture

```
┌──────────────────────────────────────────────────────────────┐
│                    User Initiates Task                       │
│            "Create Trigger Map for Källa project"            │
└──────────────────────────────────────────────────────────────┘
                              ↓
┌──────────────────────────────────────────────────────────────┐
│                  Agent Offers Mode Choice                    │
│         Workshop | Suggest | Dream                           │
└──────────────────────────────────────────────────────────────┘
                              ↓
              ┌───────────────┴───────────────┐
              ↓                               ↓
    [Workshop Mode]                  [Suggest/Dream Mode]
    Facilitate workshop              ↓
    Draw out user's ideas        Layer 1: Learn WDS Form
    (Current WDS)                    ↓
                                 Layer 2: Project Context (Cumulative)
                                     ↓
                                 Layer 3: Domain Research
                                     ↓
                                 Layer 4: Generate Artifact
                                     ↓
                                 Layer 5: Self-Review & Refine
                                     ↓
                                 Add to Layer 2 → Repeat for next step
```

---

## Files Created (Foundation)

### Core Documentation
1. **`dream-up-foundation.md`**
   - Architecture overview
   - Three engagement modes explained
   - Five-layer system design with cumulative context
   - Three knowledge sources (WDS Form, Product Brief, Domain Research)
   - Implementation roadmap

2. **`dream-up-implementation-guide.md`** (this file)
   - How to use Dream Up
   - Quick start guide
   - Agent instructions

### Templates
3. **`src/templates/dream-up-agent-dialog.template.md`**
   - Agent dialog template for Dream Up sessions
   - Works for any phase
   - Includes all five layers plus cumulative context tracking

### Quality Rubrics
4. **`dream-up-rubric-phase-2.md`**
   - Phase 2 (Trigger Mapping) quality standards
   - Completeness checklist
   - Quality criteria with examples
   - Common mistakes and best practices
   - Self-review process

5. **`dream-up-rubric-template.md`**
   - Template for creating rubrics for other phases
   - Step-by-step extraction guide
   - Ensures consistency across phases

---

## How to Use Dream Up

### For Users

**When starting a task, agent will ask:**
> Which mode would you like?
>
> - **Workshop** - We'll build it together through questions
> - **Suggest** - I'll generate and refine, you approve each step
> - **Dream** - I'll generate autonomously, you can observe and interrupt

**Choose based on:**
- **Workshop:** Discovery, strategic decisions, learning the method
- **Suggest:** Guided work, want to see thinking process
- **Dream:** Routine tasks, clear requirements, trust the agent

### For Agents

**When user requests output generation (not just questions):**

1. **Offer mode choice** (unless user has default preference)

2. **If Suggest/Dream chosen:**
   - Load `dream-up-agent-dialog.template.md`
   - Execute five-layer process:
     - **Layer 1:** Learn WDS Form from tutorials (once, static)
     - **Layer 2:** Load Product Brief, grows cumulatively with each completed artifact
     - **Layer 3:** Research domain insights per step (WebSearch)
     - **Layer 4:** Generate artifact using all three sources
     - **Layer 5:** Self-review → Refine loop, add to Layer 2 when complete

3. **Follow self-review process from rubric:**
   - Check completeness
   - Check quality criteria
   - Check for common mistakes
   - Check best practices followed
   - Calculate quality score
   - Refine if below threshold

4. **Present to user when:**
   - Quality threshold met, OR
   - Maximum iterations reached (switch to Workshop), OR
   - User requests to see current state

---

## Quick Start: Testing on Källa

### Test Case: Phase 2 Trigger Mapping

**User request:**
> "Create Trigger Map for Källa Fordonservice"

**Agent response:**
> I can create your Trigger Map in three ways:
>
> 1. **Workshop** - I'll ask you questions about business goals, user types, and driving forces
> 2. **Suggest** - I'll draft the map using your Product Brief, then refine it while you review each iteration
> 3. **Dream** - I'll autonomously create the map, you can observe my self-review process
>
> Which would you like?

**If user chooses Suggest:**

```markdown
1. Layer 1: Learn WDS Form (load Phase 2 tutorials and rubric)
2. Layer 2: Load Product Brief documents (4 files)
3. Layer 3: Research domain (e.g., "rural car mechanic customer types")
4. Layer 4: Generate Business Goals (Iteration 1)
5. Layer 5: Self-review against rubric
5. Show user: Generated content + Self-review + Refinement plan
6. Wait for approval: [Continue] [Adjust] [Stop]
7. If Continue: Generate Iteration 2
8. Repeat until quality threshold met
```

**If user chooses Dream:**

```markdown
1-4. [Same as Suggest]
5. Show running self-dialog (visible iterations)
6. NO user checkpoint (continuous)
7. User can interrupt anytime by typing
8. Present final output when complete
```

---

## Agent Instructions: Implementing Dream Up

### When to Offer Dream Up

**Offer mode choice when:**
- User requests artifact generation (Trigger Map, PRD, Design System, etc.)
- Task has established quality standards (rubric exists)
- Context is available from prior phases

**Don't offer for:**
- Pure discovery/research (no artifact to generate)
- First time through a phase (learning mode)
- User explicitly wants dialog

### Mode Selection Dialog

```
I can create your [ARTIFACT] in three ways:

**Workshop Mode** (45-60 min)
- We'll build it together through guided questions
- Best for: Strategic discovery, learning the method

**Suggest Mode** (20-30 min)
- I'll draft using your existing context, you review each iteration
- Best for: Guided refinement, seeing the thought process

**Dream Mode** (10-15 min)
- I'll generate autonomously using WDS standards, you can observe
- Best for: Routine work, clear requirements, established patterns

Which mode would you like? Or ask me to recommend based on your situation.
```

### Executing Layer 1: Learn WDS Form

**Purpose:** Agent becomes WDS methodology expert (loaded once, static)

**Read these guides:**

```markdown
Phase 2 (Trigger Mapping):
- docs/method/phase-2-trigger-mapping-guide.md
- docs/quick-start/02-trigger-mapping.md
- src/data/agent-guides/saga/trigger-mapping.md
- docs/models/impact-effect-mapping.md
- docs/method/dream-up-rubric-phase-2.md
```

**Internalize:**
- How to structure artifacts
- What makes quality vs poor output
- Common mistakes to avoid
- Best practices to follow
- Self-review process

**Document in agent dialog:**
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

### Executing Layer 2: Project Context (Cumulative)

**Purpose:** Extract business substance, grows with each step

**Initial load - Phase 1 artifacts:**

```markdown
- {output_folder}/A-Product-Brief/product-brief.md
- {output_folder}/A-Product-Brief/content-language.md
- {output_folder}/A-Product-Brief/platform-requirements.md
- {output_folder}/A-Product-Brief/visual-direction.md
```

**Cumulative growth:**
```
Initial: Product Brief
  ↓
After Business Goals: Product Brief + Business Goals
  ↓
After Target Groups: Product Brief + Business Goals + Target Groups
  ↓
After Driving Forces: All above + Driving Forces
  ↓
After Prioritization: All above + Prioritization
```

**Document in agent dialog:**
```markdown
## Layer 2: Project Context (Initial)

### Business Context
[Key facts about the business]

### Users
[Archetypes or personas mentioned]

### Constraints
[Technical, business, timeline limits]

### Strategic Direction
[Goals, positioning, priorities]

---

## Layer 2: Project Context (After Business Goals)
[Add Business Goals artifact to context above]

## Layer 2: Project Context (After Target Groups)
[Add Target Groups artifact to context above]

[etc. - grows cumulatively]
```

### Executing Layer 3: Domain Research

**Purpose:** Agent develops domain expertise (per step, as needed)

**Research process:**

1. **Identify research questions for current step**
   - Example: "rural car mechanic customer needs"
   - Example: "northern Öland tourism statistics"

2. **Execute WebSearch queries**
   - Industry insights
   - User reviews, forums
   - Competitor analysis
   - Behavioral patterns

3. **Synthesize findings**

**Document in agent dialog:**
```markdown
## Layer 3: Domain Research - Business Goals

### Research Questions
- [Question 1]
- [Question 2]

### Findings
- [Key insight 1 with source]
- [Key insight 2 with source]

### Implications
- [How this informs generation]
```

### Executing Layer 4: Generate Artifact

**Purpose:** Synthesize all three sources

**Input sources:**
- Layer 1: WDS Form (how to structure)
- Layer 2: Project Context (business substance, ALL prior artifacts)
- Layer 3: Domain Research (industry insights)

**Generation:**
1. Apply WDS structure from Layer 1
2. Use business context from Layer 2 (cumulative)
3. Enhance with insights from Layer 3
4. Create this step's artifact

### Executing Layer 5: Self-Review

**The Loop:**

```python
iteration = 1
max_iterations = 5
quality_met = False

while not quality_met and iteration <= max_iterations:
    # Generate content
    content = generate_output(context, standards)

    # Self-review
    review = self_review_against_rubric(content, rubric)

    # Log in agent dialog
    log_iteration(iteration, content, review)

    # Check threshold
    if review.meets_minimum_threshold:
        quality_met = True
    else:
        # Plan refinement
        refinement_plan = create_refinement_plan(review.gaps)

        if mode == "Suggest":
            # Show user, wait for input
            present_iteration_and_wait()
        elif mode == "Dream":
            # Show progress, continue
            show_progress()

        iteration += 1

if quality_met:
    present_final_output()
else:
    suggest_switch_to_workshop_mode()
```

### Self-Review Template

**For each iteration, document:**

```markdown
### Iteration {{N}}

**Generated:**
{{content_summary}}

**Self-Review:**

#### Completeness: {{X}}/{{Y}}
- [✅/❌] Section A
- [✅/❌] Section B

#### Quality Criteria: {{X}}/{{Y}}
- [✅/⚠️/❌] Criterion 1: [Evidence]
- [✅/⚠️/❌] Criterion 2: [Evidence]

#### Mistakes Avoided: {{X}}/{{Y}}
- [✅/❌] Avoided mistake A
- [✅/❌] Avoided mistake B

#### Best Practices: {{X}}/{{Y}}
- [✅/❌] Practice A followed
- [✅/❌] Practice B followed

**Overall Score:** {{score}}/10

**Gaps:**
1. [Gap description]
2. [Gap description]

**Refinement Needed:** [Yes/No]

{{if Suggest mode: "User Checkpoint: [Continue] [Adjust] [Stop]"}}
```

### Presenting Final Output

```markdown
## Generation Complete ✅

**Iterations:** {{count}}
**Final Quality Score:** {{score}}/10

**Artifact Location:** {{path}}

**Summary:**
{{what_was_created}}

**Key Decisions:**
{{strategic_choices_made}}

**Quality Assessment:**
- Completeness: ✅
- Quality criteria: ✅
- Mistakes avoided: ✅
- Best practices: ✅

**What's Next:**
{{next_phase_recommendation}}

Would you like to review the [ARTIFACT] or make any adjustments?
```

---

## Testing Checklist

Before testing on Källa:

- [x] Dream Up foundation documented
- [x] Agent dialog template created
- [x] Phase 2 rubric created
- [x] Rubric template for other phases created
- [x] Implementation guide complete
- [ ] Test Suggest Mode on Källa Phase 2
- [ ] Validate quality of output
- [ ] Refine thresholds if needed
- [ ] Test Dream Mode on Källa Phase 2
- [ ] Compare quality: Workshop vs Suggest vs Dream

---

## Success Criteria

**For Foundation (Current):**
- ✅ Architecture documented
- ✅ Templates created
- ✅ One rubric example complete
- ✅ Implementation guide ready

**For Testing (Next):**
- [ ] Suggest Mode produces quality output on Källa
- [ ] Self-review catches real gaps
- [ ] Refinement improves quality
- [ ] User feedback positive
- [ ] Comparable quality to Workshop Mode

**For Production (Future):**
- [ ] Rubrics for all phases
- [ ] Integrated into workflows
- [ ] User can choose mode at workflow start
- [ ] Quality metrics tracked

---

## Next Steps

1. **Test on Källa** - Phase 2 Trigger Mapping with Suggest Mode
2. **Refine rubric** - Based on real-world performance
3. **Create more rubrics** - Phases 1, 3, 4, 5, 6
4. **Integrate into workflows** - Add mode selection to workflow instructions
5. **Document lessons** - What works, what needs adjustment

---

## Questions for Testing

**During Källa test, evaluate:**

1. **Context Extraction:** Did agent extract right info from Product Brief?
2. **Standards Loading:** Did rubric provide clear guidance?
3. **Generation Quality:** First iteration quality level?
4. **Self-Review Accuracy:** Did agent catch real gaps?
5. **Refinement Effectiveness:** Did iterations improve quality?
6. **Threshold Calibration:** Were thresholds set right?
7. **User Experience:** Was process clear and trustworthy?
8. **Time Savings:** Faster than Workshop Mode?
9. **Quality Comparison:** As good as Workshop Mode?
10. **Interrupt Capability:** Could user guide/stop effectively?

---

## Ready to Test

**Foundation is complete.**

**To test on Källa:**
> "Let's test Dream Up Suggest Mode on Källa Phase 2 Trigger Mapping"

**What will happen:**
1. Agent loads Product Brief context (already done)
2. Agent loads Phase 2 rubric (already created)
3. Agent generates Iteration 1 of Trigger Map
4. Agent self-reviews against rubric
5. Agent shows you content + review + refinement plan
6. You approve or adjust
7. Agent iterates until quality threshold met
8. You get final Trigger Map for Källa project

---

*Dream Up Foundation v0.1.0 - Ready for real-world testing*
