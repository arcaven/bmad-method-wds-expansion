# Dream Up Quality Rubric: Phase 2 (Trigger Mapping)

**Purpose:** Standards for agent self-review when generating Trigger Maps in Suggest or Dream mode.

**Source Standards:**
- `docs/method/phase-2-trigger-mapping-guide.md`
- `src/data/agent-guides/saga/trigger-mapping.md`
- `docs/models/impact-effect-mapping.md`

---

## Completeness Checklist

A complete Trigger Map includes:

- [ ] **Business Goals Layer** (3×3 Structure)
  - [ ] Exactly 3 visionary goals (sometimes 4-5 if truly necessary)
  - [ ] Each goal has exactly 3 objectives (sometimes 4-5 if truly necessary)
  - [ ] Goals ordered hierarchically (primary outcome first, then prerequisites)
  - [ ] Goals are aspirational, not metrics (e.g., "Become more profitable" not "Increase revenue 10%")
  - [ ] Each objective aligns with its parent goal (e.g., work-life balance → Work Smarter)
  - [ ] Clear connection: which goals the product serves

- [ ] **Product/Solution Hub**
  - [ ] Product name
  - [ ] Brief description of what it does
  - [ ] Positioned as connection between goals and users

- [ ] **Target Groups Layer**
  - [ ] 3-4 user types maximum (not more!)
  - [ ] Each connected to specific business goals they serve
  - [ ] Priority ranking (Primary, Secondary, Tertiary)

- [ ] **Detailed Personas**
  - [ ] Each target group has detailed profile
  - [ ] Alliterative naming (e.g., "Patrick the Professional")
  - [ ] Psychological depth (not just demographics)
  - [ ] Usage context clearly defined

- [ ] **Usage Goals (Driving Forces)**
  - [ ] Positive drivers for each persona (3-5 per persona)
  - [ ] Negative drivers for each persona (3-5 per persona)
  - [ ] Both types present and balanced
  - [ ] Contextual (usage goals, not life goals)

- [ ] **Prioritization**
  - [ ] Business goals ranked
  - [ ] Target groups ranked
  - [ ] Driving forces ranked (per persona)

- [ ] **Optional: Feature Impact Analysis**
  - [ ] Feature list with impact scores
  - [ ] Mapping to target groups and drivers
  - [ ] Priority ranking based on strategic value

- [ ] **Visual Diagram (Optional but Recommended)**
  - [ ] Mermaid diagram showing connections
  - [ ] Left-to-right flow: Goals → Product → Groups → Drivers
  - [ ] Color coding (green positive, red negative)

---

## Quality Criteria

### 1. Strategic Depth (vs. Surface Level)

**❌ Shallow:**
> "Users want convenience and efficiency"

**✅ Deep:**
> "Tomas the Tourist is stressed and unfamiliar with Öland. He wants immediate reassurance that help is available (positive driver: 'Get back on road quickly'). He fears being stuck or getting ripped off by unknown mechanic (negative driver: 'Fear of being stranded or overcharged')."

**Self-Check:**
- Does each driving force reveal specific psychology?
- Can I design a feature to address this specific force?
- Would two different designers interpret this the same way?

---

### 2. Usage Context Clarity (vs. Life Goals)

**❌ Wrong (Life Goals):**
> "Harriet wants to be successful and respected"

**✅ Right (Usage Goals):**
> "When using the booking platform, Harriet wants to project authority and professionalism to her clients (not feel like a beginner)"

**Self-Check:**
- Are driving forces tied to the specific usage context?
- Have I avoided generic life aspirations?
- Is it clear WHEN this goal is active?

---

### 3. Persona Depth (vs. Demographics)

**❌ Shallow Demographics:**
> "Sarah, 35, consultant, lives in London"

**✅ Psychological Depth:**
> "Sophie the Solo Consultant has been independent for 3 years. She's confident in her expertise but anxious about looking unprepared in front of clients. Every proposal feels like her reputation is on the line."

**Self-Check:**
- Can I feel empathy for this person?
- Do I understand their internal state?
- Does this inform design decisions?

---

### 4. Negative Drivers Present (vs. Only Positive)

**❌ Only Positive:**
> Users want:
> - Professional appearance
> - Time savings
> - Easy formatting

**✅ Positive + Negative:**
> Positive Drivers:
> - Feel prepared and confident
> - Look professional to clients
>
> Negative Drivers:
> - Fear looking unprepared or amateur
> - Frustration with wasted time on formatting
> - Anxiety about making embarrassing mistakes

**Self-Check:**
- Do I have roughly equal positive and negative drivers?
- Are negative drivers specific fears/frustrations (not just inverse of positive)?
- Do negative drivers feel visceral and urgent?

---

### 5. Focused Scope (vs. Too Many Groups)

**❌ Too Many:**
> 8 target groups with 50+ driving forces

**✅ Focused:**
> 3-4 target groups, deeply understood, with 3-5 key drivers each

**Self-Check:**
- Have I kept to 3-4 target groups maximum?
- Can I clearly articulate why each group matters?
- Is each group genuinely different in psychology?

---

### 6. Actionable Specificity (vs. Vague)

**❌ Vague:**
> "Want a better experience"

**✅ Actionable:**
> "Want to find phone number within 3 seconds without scrolling (stressed tourist context)"

**Self-Check:**
- Can a designer create a feature from this?
- Is it specific enough to test/measure?
- Does it paint a clear picture?

---

### 7. Business Goal Connection (vs. Floating Users)

**❌ Disconnected:**
> Here are 4 user types [no connection to business goals]

**✅ Connected:**
> Business Goal: "Reduce repetitive phone calls"
> → Serves: Tomas the Tourist (high volume, common questions)
> → Also serves: Lennart the Local (checking hours)

**Self-Check:**
- Can I trace each user type to a business goal?
- Is it clear HOW their success drives business success?
- Have I avoided including users "just because they exist"?

---

## Common Mistakes to Avoid

### ❌ Mistake 1: Solutions on the Map
**Problem:** Including features/solutions in the Trigger Map itself

**Example:** "Users want → Template library with 20 designs"

**Why bad:** Map ages quickly, locks in solutions too early

**Self-Check:**
- Have I kept solutions out of driving forces?
- Are driving forces about psychology, not features?

---

### ❌ Mistake 2: Generic/Obvious Forces
**Problem:** Driving forces that apply to every product

**Example:** "Want it to be easy" / "Want to save time" / "Want good value"

**Why bad:** Doesn't inform design decisions

**Self-Check:**
- Are driving forces specific to this product/context?
- Would they still be true for a different product?
- Do they reveal insight or just state obvious?

---

### ❌ Mistake 3: Demographic Personas
**Problem:** Describing who they are, not how they think

**Example:** "Male, 45, manager, uses iPhone, married with kids"

**Why bad:** Demographics don't drive design decisions

**Self-Check:**
- Have I focused on psychology over demographics?
- Can I design for this person's internal state?
- Does knowing their age/device actually matter?

---

### ❌ Mistake 4: Inconsistent Priority
**Problem:** Everything marked as Priority 1

**Example:** "All 4 target groups are equally important"

**Why bad:** Loses strategic focus, can't make trade-off decisions

**Self-Check:**
- Have I made hard choices about priority?
- Is there a clear Primary user?
- Can I defend why Group A ranks above Group B?

---

### ❌ Mistake 5: Metrics as Goals (CRITICAL)
**Problem:** Treating measurements as visionary business goals

**Example:**
- ❌ "Business Goal: Reduce phone calls 40%"
- ❌ "Business Goal: Achieve page 1 Google ranking"
- ❌ "Business Goal: 150K revenue by Q4"

**Why bad:** Metrics are not aspirational - they don't fill you with excitement or purpose. A goal should be visionary; metrics measure progress toward that vision.

**Correct Structure:**
```
Business Goal: Work smarter (visionary aspiration)
  └─ Measured by: 40% reduction in repetitive info calls

Business Goal: Constant customer flow (visionary aspiration)
  └─ Measured by: Page 1 ranking for key terms, 50 new customers/month
```

**Self-Check:**
- Are my business goals inspirational statements about what the business wants to BE?
- Do the goals remain relevant even if tactics change?
- Are metrics attached as measurements, not stated as the goals themselves?
- Would these goals fill the business owner with excitement and purpose?

---

### ❌ Mistake 6: Violating 3×3 Structure (STRUCTURAL)
**Problem:** Too many goals or objectives, diluting focus

**Example:**
- ❌ 7 business goals with varying numbers of objectives
- ❌ Goal 1 has 2 objectives, Goal 2 has 6 objectives, Goal 3 has 4 objectives (inconsistent)
- ❌ Freeform list of 15+ measurements without clear goal grouping

**Why bad:** Loses strategic focus, makes prioritization impossible, overwhelming to use

**Correct Structure:**
```
3 Goals × 3 Objectives Each = 9 Total Measurements

Goal 1: [Primary Outcome]
  1.1, 1.2, 1.3

Goal 2: [Prerequisite]
  2.1, 2.2, 2.3

Goal 3: [Prerequisite]
  3.1, 3.2, 3.3
```

**Self-Check:**
- Do I have exactly 3 visionary goals? (or 4-5 if truly necessary with justification)
- Does each goal have exactly 3 objectives? (or 4-5 if truly necessary)
- Is Goal 1 the primary outcome, Goals 2-3 the prerequisites?
- Are objectives properly aligned with their parent goals?

---

## Best Practices to Follow

### ✅ Practice 1: Alliterative Persona Names
Use memorable names that hint at their role:
- Patrick the Professional (efficiency-focused)
- Sophie the Socializer (community-driven)
- Tomas the Tourist (stressed, unfamiliar)

**Why:** Memorable, sets tone, easy to reference

---

### ✅ Practice 2: Equal Weight to Negative Drivers
Give as much attention to fears/frustrations as wishes

**Why:** Loss aversion is powerful - people act to avoid pain

---

### ✅ Practice 3: Context Declaration
Explicitly state the usage context for goals

**Example:** "In the context of emergency car trouble on vacation, Tomas wants..."

**Why:** Prevents confusion between contexts, keeps goals focused

---

### ✅ Practice 4: Visual Connection
Create visual diagram showing goal → product → user → force flow

**Why:** Makes connections explicit, easier to validate logic

---

## Self-Review Process

When generating a Trigger Map, review in this order:

### 1. Completeness (5 min)
- Run through completeness checklist above
- Mark what's present vs. missing
- If major sections missing: Generate those first

### 2. Quality Criteria (10 min)
- Check each of the 7 quality criteria
- Score each: ✅ (met), ⚠️ (partial), ❌ (gap)
- Document specific gaps

### 3. Common Mistakes (5 min)
- Check for each of the 6 common mistakes
- Flag any instances found
- Plan corrections

### 4. Best Practices (5 min)
- Check which best practices followed
- Identify opportunities to apply more
- Enhance if needed

### 5. Overall Assessment
```markdown
## Self-Review Summary

**Completeness:** [X/10 sections complete]
**Quality Score:** [X/7 criteria fully met]
**Mistakes:** [X/6 mistakes avoided]
**Best Practices:** [X/4 practices followed]

**Overall Quality:** [Excellent/Good/Needs Work]

**Key Gaps:**
1. [Gap description]
2. [Gap description]

**Refinement Needed:** [Yes/No]
```

---

## Quality Thresholds

### Minimum (Must Meet to Present to User)
- Completeness: 8/10 sections
- Quality Score: 5/7 criteria fully met
- Mistakes: 6/6 avoided (all mistakes must be avoided)
- Best Practices: 2/4 followed

### Excellent (High Confidence)
- Completeness: 10/10 sections
- Quality Score: 7/7 criteria fully met
- Mistakes: 5/5 avoided
- Best Practices: 4/4 followed

### Maximum Iterations
- If not meeting Minimum threshold after 5 iterations
- Switch to Workshop Mode (agent asks user questions)
- Something needs human insight

---

## Example Self-Review

```markdown
## Self-Review: Källa Fordonservice Trigger Map (Iteration 1)

### Completeness Check
- [✅] Business Goals Layer (vision + 3 SMART objectives)
- [✅] Product Hub (Källa website described)
- [✅] Target Groups (4 personas: Tomas, Lennart, Fredrik, Maria)
- [✅] Detailed Personas (psychological depth, alliterative names)
- [✅] Positive Drivers (3-5 per persona)
- [✅] Negative Drivers (3-5 per persona)
- [✅] Prioritization (groups ranked)
- [❌] Feature Impact Analysis (not done yet - optional)
- [❌] Visual Diagram (not done yet)

**Completeness: 7/9 (acceptable, optional items missing)**

### Quality Criteria
1. **Strategic Depth:** ✅ - Drivers reveal specific psychology (e.g., "Fear being stranded on vacation")
2. **Usage Context:** ✅ - Clear contexts (tourist searching, local checking hours)
3. **Persona Depth:** ✅ - Rich psychological profiles beyond demographics
4. **Negative Drivers:** ✅ - Balanced positive/negative, visceral fears present
5. **Focused Scope:** ✅ - 4 target groups, each distinct
6. **Actionable Specificity:** ⚠️ - Some drivers could be more specific (e.g., "want peace of mind" → "want confirmation that mechanic is certified and trustworthy")
7. **Business Connection:** ✅ - Each persona clearly serves business goals

**Quality Score: 6/7 (one partial)**

### Common Mistakes
- [✅] No solutions on map (avoided)
- [✅] Drivers are specific, not generic (avoided)
- [✅] Personas are psychological, not demographic (avoided)
- [✅] Clear prioritization with Primary user (avoided)
- [✅] Business goals are visionary, not metrics (avoided)
- [✅] 3×3 structure maintained (avoided violating)

**Mistakes Avoided: 6/6**

### Best Practices
- [✅] Alliterative names (Tomas the Tourist, Lennart the Local, etc.)
- [✅] Equal weight to negative drivers
- [✅] Context explicitly stated
- [❌] No visual diagram yet

**Best Practices: 3/4**

### Overall Assessment
**Quality Score:** 8.5/10
**Overall:** Good - meets minimum threshold, one refinement opportunity

**Key Gap:**
1. Some driving forces could be more actionable/specific

**Refinement Plan:**
- Iteration 2: Sharpen vague drivers ("peace of mind" → specific trust signals)
- Add visual diagram (optional but enhances clarity)

**Refinement Needed:** Yes (minor)
```

---

*This rubric guides agent self-review to ensure Trigger Maps meet WDS quality standards.*
