# Dream Up Quality Rubric Template

**Purpose:** Template for creating quality rubrics for any WDS phase/workflow

**How to Use:** When implementing Dream Up for a new phase, extract quality criteria from that phase's guides and tutorials using this structure.

---

## Rubric Structure

Every Dream Up quality rubric should include:

1. **Completeness Checklist** - What must be present
2. **Quality Criteria** - What makes it good (with examples)
3. **Common Mistakes** - What to avoid (with examples)
4. **Best Practices** - What to aspire to (with examples)
5. **Self-Review Process** - Step-by-step checking guide
6. **Quality Thresholds** - Minimum/excellent standards

---

## 1. Completeness Checklist

**Purpose:** Ensure all required components are present

**Format:**
```markdown
## Completeness Checklist

A complete [Phase/Task Output] includes:

- [ ] **[Component 1]**
  - [ ] [Sub-element A]
  - [ ] [Sub-element B]

- [ ] **[Component 2]**
  - [ ] [Sub-element C]
  - [ ] [Sub-element D]

- [ ] **[Component 3]**
  - [ ] [Required section/artifact]
```

**How to Extract:**
- Read phase guide's "What You'll Create" section
- Read workflow templates
- Check step files for required outputs
- List all "must have" elements

---

## 2. Quality Criteria

**Purpose:** Define what separates good from poor quality

**Format:**
```markdown
## Quality Criteria

### 1. [Criterion Name] (vs. [Opposite])

**❌ Poor Example:**
> [Quote showing what NOT to do]

**✅ Good Example:**
> [Quote showing what to do instead]

**Self-Check:**
- [Question to validate this criterion]
- [Another validation question]
- [Third validation question]

---

### 2. [Another Criterion]
[Same structure...]
```

**How to Extract:**
- Find "good vs bad" examples in tutorials
- Look for "tips" or "what makes X effective"
- Check phase guide for quality indicators
- Identify depth/specificity/actionability standards

**Common Quality Dimensions:**
- **Depth** (surface-level vs. profound)
- **Specificity** (vague vs. concrete)
- **Actionability** (theoretical vs. usable)
- **Connection** (isolated vs. linked to strategy)
- **Completeness** (partial vs. thorough)

---

## 3. Common Mistakes

**Purpose:** Flag anti-patterns to avoid

**Format:**
```markdown
## Common Mistakes to Avoid

### ❌ Mistake 1: [Mistake Name]
**Problem:** [What the mistake is]

**Example:** [Quote showing the mistake]

**Why bad:** [Why this is problematic]

**Self-Check:**
- [Question to detect this mistake]
- [Another detection question]

---

### ❌ Mistake 2: [Another Mistake]
[Same structure...]
```

**How to Extract:**
- Check phase guides for "avoid" or "don't" sections
- Look for "common pitfalls" in tutorials
- Find "wrong approach" examples
- Identify repeated failure patterns

---

## 4. Best Practices

**Purpose:** Highlight excellence patterns

**Format:**
```markdown
## Best Practices to Follow

### ✅ Practice 1: [Practice Name]
[Description of the practice]

**Example:** [Demonstration]

**Why:** [Benefit/rationale]

---

### ✅ Practice 2: [Another Practice]
[Same structure...]
```

**How to Extract:**
- Find "best practices" sections in guides
- Look for "pro tips" or "expert advice"
- Identify patterns in example projects
- Note what makes excellent outputs stand out

---

## 5. Self-Review Process

**Purpose:** Step-by-step checking guide

**Format:**
```markdown
## Self-Review Process

When generating a [Task Output], review in this order:

### 1. Completeness ([Time estimate])
- Run through completeness checklist above
- Mark what's present vs. missing
- If major sections missing: Generate those first

### 2. Quality Criteria ([Time estimate])
- Check each quality criterion
- Score each: ✅ (met), ⚠️ (partial), ❌ (gap)
- Document specific gaps

### 3. Common Mistakes ([Time estimate])
- Check for each common mistake
- Flag any instances found
- Plan corrections

### 4. Best Practices ([Time estimate])
- Check which best practices followed
- Identify opportunities to apply more
- Enhance if needed

### 5. Overall Assessment
```markdown
## Self-Review Summary

**Completeness:** [X/Y sections complete]
**Quality Score:** [X/Y criteria fully met]
**Mistakes:** [X/Y mistakes avoided]
**Best Practices:** [X/Y practices followed]

**Overall Quality:** [Excellent/Good/Needs Work]

**Key Gaps:**
1. [Gap description]
2. [Gap description]

**Refinement Needed:** [Yes/No]
```
```

**How to Design:**
- Sequence checks logically (completeness first)
- Estimate realistic time for each step
- Make assessment objective (clear criteria)
- Include summary template

---

## 6. Quality Thresholds

**Purpose:** Define when output is ready

**Format:**
```markdown
## Quality Thresholds

### Minimum (Must Meet to Present to User)
- Completeness: [X/Y sections]
- Quality Score: [X/Y criteria fully met]
- Mistakes: [Y/Y avoided (all)]
- Best Practices: [X/Y followed]

### Excellent (High Confidence)
- Completeness: [Y/Y sections (all)]
- Quality Score: [Y/Y criteria fully met (all)]
- Mistakes: [Y/Y avoided (all)]
- Best Practices: [Y/Y followed (all)]

### Maximum Iterations
- If not meeting Minimum threshold after 5 iterations
- Switch to Workshop Mode (agent asks user questions)
- Something needs human insight
```

**How to Set:**
- **Minimum:** What's acceptable for user review
- **Excellent:** What represents best-in-class
- **Iteration limit:** Prevent infinite loops (5 is reasonable)

---

## Example: Creating Rubric for Phase X

### Step 1: Gather Source Materials
```
Phase guides:
- docs/method/phase-X-guide.md
- docs/quick-start/0X-phase-name.md

Workflow files:
- src/workflows/X-phase-name/instructions.md
- src/workflows/X-phase-name/templates/

Agent guides:
- src/data/agent-guides/[agent-name]/phase-x.md

Models:
- docs/models/[relevant-model].md
```

### Step 2: Extract Completeness
Read through templates and workflow steps:
- What sections must exist?
- What components are required?
- What artifacts get generated?

→ Create completeness checklist

### Step 3: Extract Quality Criteria
Find examples of good vs poor in guides:
- What makes output "effective"?
- What separates amateur from expert?
- What dimensions matter (depth, specificity, etc.)?

→ Create quality criteria with examples

### Step 4: Extract Mistakes
Find warnings and "avoid" sections:
- What do beginners commonly do wrong?
- What anti-patterns exist?
- What breaks the methodology?

→ Create common mistakes list

### Step 5: Extract Best Practices
Find "pro tips" and excellence markers:
- What do experts do?
- What patterns appear in great examples?
- What makes output exceptional?

→ Create best practices list

### Step 6: Design Self-Review Process
Create checking sequence:
- Logical order (completeness → quality → mistakes → practices)
- Time estimates (be realistic)
- Clear scoring system

→ Create self-review steps

### Step 7: Set Thresholds
Define quality bars:
- Minimum: What's acceptable?
- Excellent: What's aspirational?
- Iteration limit: When to stop?

→ Create threshold definitions

### Step 8: Validate with Example
Test the rubric:
- Take an example output
- Run through self-review
- Does it catch real issues?
- Is it too strict or too lenient?

→ Refine thresholds and criteria

---

## Rubric Maintenance

**When to Update Rubrics:**
- New best practices discovered
- Common mistakes patterns emerge
- Quality standards evolve
- User feedback on agent output

**Version Control:**
- Version rubrics (v1.0, v1.1, etc.)
- Document what changed and why
- Keep changelog in rubric file

---

## Rubric Naming Convention

```
dream-up-rubric-[phase-or-task].md
```

**Examples:**
- `dream-up-rubric-phase-1.md` (Product Brief)
- `dream-up-rubric-phase-2.md` (Trigger Mapping)
- `dream-up-rubric-phase-3.md` (Platform Requirements)
- `dream-up-rubric-phase-4-scenarios.md` (Scenario Outlining)
- `dream-up-rubric-phase-5-design-system.md` (Design Tokens)

---

## Quality Rubric Checklist

Use this to validate your rubric:

- [ ] **Completeness Checklist** exists and is comprehensive
- [ ] **Quality Criteria** have clear good/bad examples
- [ ] **Common Mistakes** are specific and detectable
- [ ] **Best Practices** are actionable
- [ ] **Self-Review Process** is step-by-step with time estimates
- [ ] **Quality Thresholds** are defined (minimum/excellent)
- [ ] **Example Self-Review** demonstrates usage
- [ ] Rubric is objective (different agents would score the same)
- [ ] Rubric aligns with phase guide and tutorials
- [ ] Rubric has been tested with real output

---

## Next Steps

1. **Create Phase 1 rubric** (Product Brief + companions)
2. **Create Phase 3 rubric** (Platform Requirements)
3. **Create Phase 4 rubrics** (Scenarios, Storyboards, Specs)
4. **Create Phase 5 rubric** (Design System)
5. **Create Phase 6 rubric** (Delivery documents)

Each rubric enables Dream Up for that phase.

---

*This template ensures consistent quality standards across all WDS phases.*
