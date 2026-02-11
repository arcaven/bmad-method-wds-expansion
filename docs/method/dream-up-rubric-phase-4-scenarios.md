# Dream Up Quality Rubric: Phase 4 (Scenario Outlining)

**Purpose:** Standards for agent self-review when generating user journey scenarios in Suggest or Dream mode.

**Source Standards:**
- `src/workflows/4-ux-design/steps/step-02-substeps/scenario-init/`
- `docs/quick-start/04-outline-scenarios.md`
- `docs/method/phase-4-ux-design-guide.md`

---

## Completeness Checklist

A complete scenario outline includes:

- [ ] **Core Feature Definition**
  - [ ] Clear statement of what feature/experience the scenario covers
  - [ ] Aligned with business goals from Trigger Map
  - [ ] Aligned with primary target group needs

- [ ] **Entry Point**
  - [ ] Specific starting location/context (e.g., "Google search results page")
  - [ ] Clear description of HOW user arrives (search, link, ad, etc.)
  - [ ] Realistic entry path for target persona

- [ ] **Mental State**
  - [ ] Emotional state described (stressed, curious, confident, etc.)
  - [ ] Connected to persona's driving forces from Trigger Map
  - [ ] Three components present:
    - [ ] Trigger: What just happened
    - [ ] Hope: What they're hoping for
    - [ ] Worry: What they're worried about

- [ ] **Success Goals (Mutual Value)**
  - [ ] **Business Success:** What the business achieves when scenario completes
  - [ ] **User Success:** What the user achieves when scenario completes
  - [ ] Both are specific and measurable
  - [ ] Clear mutual benefit (not zero-sum)

- [ ] **Shortest Path (Linear Flow)**
  - [ ] Pages/steps listed in sequential order
  - [ ] Each step has name + brief description
  - [ ] No branches or "what if" variations (sunshine path only)
  - [ ] Minimum viable steps (no unnecessary pages)
  - [ ] Each step moves user toward mutual success

- [ ] **Scenario Naming**
  - [ ] Clear, descriptive scenario name (e.g., "Hasse's Emergency Search")
  - [ ] Scenario ID assigned (S01, S02, etc.)
  - [ ] URL-friendly slug (e.g., `01-hasses-emergency-search`)

- [ ] **Trigger Map Connections**
  - [ ] Linked to specific persona(s) from Trigger Map
  - [ ] Addresses specific driving forces
  - [ ] Serves specific business goal(s)

---

## Quality Criteria

### 1. Persona Alignment (vs. Generic User)

**❌ Generic:**
> "User visits website, signs up, completes profile"

**✅ Persona-Specific:**
> "Hasse the Motorhome Owner (stressed tourist, broken RV, unfamiliar with area) visits website via Google search 'motorhome repair Öland'. He needs immediate confirmation Björn can help, plus location/hours, within 10 seconds before calling."

**Self-Check:**
- Can I identify which persona this scenario serves?
- Does mental state match persona's psychological profile?
- Do entry point and flow reflect persona's behavior patterns?

---

### 2. Mental State Richness (vs. Shallow Description)

**❌ Shallow:**
> "User is interested in the product"

**✅ Rich:**
> **Mental State:** Panicked and overwhelmed
> - **Trigger:** Motorhome just broke down in Byxelkrok parking lot, family vacation at risk
> - **Hope:** Find trustworthy mechanic nearby who fixes motorhomes, get back on road today
> - **Worry:** Being stranded for days, getting ripped off by unknown mechanic, ruining family vacation

**Self-Check:**
- Can I feel the user's emotional state?
- Are all three components (Trigger/Hope/Worry) present and specific?
- Does this inform design decisions (e.g., prioritize reassurance over features)?

---

### 3. Mutual Success Clarity (vs. Vague Outcomes)

**❌ Vague:**
> Business: "Get more customers"
> User: "Successfully use the site"

**✅ Clear:**
> **Business Success:** High-intent tourist call captured + positioned as emergency-capable + builds trust for booking
> **User Success:** Confirmed Björn fixes motorhomes + has location/hours + feels confident calling (10-second validation)

**Self-Check:**
- Can I measure when each success is achieved?
- Is business success specific (not just "revenue" or "engagement")?
- Is user success tangible (not just "satisfied" or "happy")?

---

### 4. Sunshine Path Focus (vs. Branching Scenarios)

**❌ Branching:**
> 1. Landing page
> 2. If new user → signup; If returning → login
> 3. If email invalid → error; If valid → continue
> 4. If payment fails → retry; If succeeds → confirmation

**✅ Linear Sunshine Path:**
> 1. Landing page - sees value prop, clicks "Get Started"
> 2. Signup form - enters email/password
> 3. Welcome screen - confirmed, ready to explore
> 4. Dashboard - first success moment

**Self-Check:**
- Is the path completely linear (no "if" statements)?
- Have I deferred error states and edge cases?
- Is this the absolute happiest path (minimum friction)?

---

### 5. Minimum Viable Steps (vs. Over-Designed Flow)

**❌ Too Many Steps:**
> 1. Landing page
> 2. Value prop explainer page
> 3. Feature comparison page
> 4. Pricing page
> 5. Testimonials page
> 6. FAQ page
> 7. Signup page
> (7 steps before signup)

**✅ Minimum Steps:**
> 1. Landing page - value prop + CTA
> 2. Signup page - commit to trying
> 3. Welcome screen - ready to use
> (3 steps to value)

**Self-Check:**
- Can I remove any step without breaking the flow?
- Does each step move meaningfully toward success?
- Am I designing for speed or thoroughness? (Choose based on persona!)

---

### 6. Entry Point Realism (vs. Idealized Start)

**❌ Idealized:**
> "User opens app"

**✅ Realistic:**
> "Tourist googles 'car repair Öland' on mobile while parked at gas station, clicks top organic result, lands on homepage"

**Self-Check:**
- How did the user ACTUALLY discover this?
- What device are they on?
- What's their context (rushed, relaxed, multitasking)?

---

### 7. Connection to Business Goals (vs. User-Only Focus)

**❌ User-Only:**
> "User successfully books appointment (no business value mentioned)"

**✅ Connected:**
> **Business Goal:** Reduce repetitive info calls (Goal 3.1: 40% reduction)
> **How Scenario Helps:** Tourist gets hours/location/capability confirmed via website (no phone call needed for info)
> **User Success:** Found info without calling
> **Business Success:** One fewer interruption for Björn

**Self-Check:**
- Can I trace this scenario to a specific business goal from Trigger Map?
- Is the business value explicit, not assumed?
- Does user success drive business success (not compete with it)?

---

## Common Mistakes to Avoid

### ❌ Mistake 1: Edge Cases in Sunshine Path
**Problem:** Including error states, branches, or "what if" scenarios

**Example:** "User enters email. If invalid, show error. If valid, send confirmation. If email bounces, retry."

**Why bad:** Clutters the core flow, delays design focus on happy path

**Self-Check:**
- Have I removed all "if" statements?
- Am I assuming everything works perfectly?
- Have I documented edge cases separately?

---

### ❌ Mistake 2: Feature-First (Not Goal-First)
**Problem:** Starting with features instead of user goals

**Example:** "Scenario: User explores the dashboard feature"

**Why bad:** Features don't motivate design; goals do

**Correct:**
- ❌ "Scenario: Dashboard exploration"
- ✅ "Scenario: Lars checks workshop hours quickly (goal: confirm open before driving over)"

**Self-Check:**
- Does scenario name describe user GOAL or FEATURE?
- Can I remove the feature and still understand the goal?

---

### ❌ Mistake 3: Omitting Mental State
**Problem:** Only describing actions, not internal state

**Example:** "User clicks button, fills form, submits"

**Why bad:** Misses opportunity to design for emotional needs

**Self-Check:**
- Have I described Trigger/Hope/Worry?
- Can I feel the user's emotional state?
- Does mental state inform design priorities?

---

### ❌ Mistake 4: Vague Page Descriptions
**Problem:** Page names without purpose descriptions

**Example:**
> 1. Homepage
> 2. Services page
> 3. Contact page

**Why bad:** Doesn't clarify what user accomplishes at each step

**Correct:**
> 1. **Homepage** - Confirms workshop fixes motorhomes + shows location
> 2. **Contact page** - Gets phone number + directions
> 3. **Call to Björn** - Books appointment

**Self-Check:**
- Does each step have name + purpose?
- Can I explain WHY this step exists?
- Does description focus on user achievement (not just page name)?

---

### ❌ Mistake 5: Generic Personas (Not From Trigger Map)
**Problem:** Inventing personas instead of using Trigger Map personas

**Example:** "A user wants to book a service"

**Why bad:** Loses strategic alignment, wastes prior work

**Self-Check:**
- Is this scenario for a specific persona from the Trigger Map?
- Have I referenced persona's driving forces?
- Does entry point match persona's discovery pattern?

---

### ❌ Mistake 6: No Business Value
**Problem:** User-focused scenario without business success defined

**Example:**
> User Success: Booked appointment easily
> Business Success: [not mentioned]

**Why bad:** Can't evaluate if scenario is strategically valuable

**Self-Check:**
- Have I defined business success explicitly?
- Is business value measurable?
- Does it connect to business goals from Trigger Map?

---

## Best Practices to Follow

### ✅ Practice 1: Name Scenarios After Personas
Use persona name in scenario title for clarity

**Example:**
- "Hasse's Emergency Search" (not "Motorhome Repair Booking")
- "Lars Checks Hours" (not "Hours Lookup")
- "Åke Coordinates Timing" (not "Service Scheduling")

**Why:** Keeps persona psychology front-of-mind, easier to reference

---

### ✅ Practice 2: Start With Highest-Value Persona
Design scenarios for Primary persona first, then Secondary

**Why:** Ensures core value is nailed before expanding

---

### ✅ Practice 3: One Scenario Per Core Job
Each scenario should accomplish ONE clear job-to-be-done

**Why:** Keeps scenarios focused, prevents scope creep

---

### ✅ Practice 4: Connect to Driving Forces Explicitly
Link scenario to specific driving forces from Trigger Map

**Example:**
> **Driving Forces Addressed:**
> - Positive: "Immediate reassurance" (15/15 priority)
> - Negative: "Fear of being stranded" (15/15 priority)

**Why:** Validates strategic alignment, informs design priorities

---

## Self-Review Process

When generating a scenario outline, review in this order:

### 1. Completeness (3 min)
- Run through completeness checklist
- Mark what's present vs. missing
- If major sections missing: Generate those first

### 2. Quality Criteria (5 min)
- Check each of the 7 quality criteria
- Score each: ✅ (met), ⚠️ (partial), ❌ (gap)
- Document specific gaps

### 3. Common Mistakes (3 min)
- Check for each of the 6 common mistakes
- Flag any instances found
- Plan corrections

### 4. Best Practices (2 min)
- Check which best practices followed
- Identify opportunities to apply more

### 5. Overall Assessment
```markdown
## Self-Review Summary

**Completeness:** [X/7 sections complete]
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
- Completeness: 6/7 sections (Trigger Map Connections can be implicit)
- Quality Score: 5/7 criteria fully met
- Mistakes: 6/6 avoided (all mistakes must be avoided)
- Best Practices: 2/4 followed

### Excellent (High Confidence)
- Completeness: 7/7 sections
- Quality Score: 7/7 criteria fully met
- Mistakes: 6/6 avoided
- Best Practices: 4/4 followed

### Maximum Iterations
- If not meeting Minimum threshold after 5 iterations
- Switch to Workshop Mode (agent asks user questions)
- Something needs human insight

---

## Example Self-Review

```markdown
## Self-Review: Källa "Hasse's Emergency Search" Scenario (Iteration 1)

### Completeness Check
- [✅] Core Feature (website info lookup for stressed tourist)
- [✅] Entry Point (Google search "motorhome repair Öland" from parking lot)
- [✅] Mental State (Trigger: RV broke down; Hope: find nearby help; Worry: stranded/ripped off)
- [✅] Business Success (reduce info call + build trust)
- [✅] User Success (confirm capability + location in <10 sec)
- [✅] Shortest Path (3 steps: Google → Homepage → Call)
- [✅] Scenario Name ("Hasse's Emergency Search", S01)
- [✅] Trigger Map Connections (Hasse persona, "Immediate reassurance" driver)

**Completeness: 7/7**

### Quality Criteria
1. **Persona Alignment:** ✅ - Clear Hasse persona, matches psychological profile
2. **Mental State Richness:** ✅ - All three components (Trigger/Hope/Worry) present and visceral
3. **Mutual Success:** ✅ - Both successes specific and measurable
4. **Sunshine Path:** ✅ - Linear, no branches
5. **Minimum Steps:** ✅ - Only 3 steps to value
6. **Entry Point Realism:** ✅ - Realistic mobile search behavior
7. **Business Goal Connection:** ✅ - Explicitly tied to Goal 3.1 (reduce calls)

**Quality Score: 7/7**

### Common Mistakes
- [✅] No edge cases in path (avoided)
- [✅] Goal-first, not feature-first (avoided)
- [✅] Mental state present (avoided)
- [✅] Page descriptions specific (avoided)
- [✅] Used Trigger Map persona (avoided)
- [✅] Business value defined (avoided)

**Mistakes Avoided: 6/6**

### Best Practices
- [✅] Scenario named after persona ("Hasse's Emergency Search")
- [✅] Started with highest-value persona (Primary: Hasse for tourists)
- [✅] One clear job-to-be-done (validate capability quickly)
- [✅] Linked to driving forces ("Immediate reassurance" 15/15)

**Best Practices: 4/4**

### Overall Assessment
**Quality Score:** 10/10
**Overall:** Excellent - exceeds minimum threshold

**Key Gaps:** None

**Refinement Needed:** No
```

---

*This rubric guides agent self-review to ensure scenario outlines meet WDS quality standards and align with Trigger Map insights.*
