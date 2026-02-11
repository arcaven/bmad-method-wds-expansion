# Phase 2: Trigger Mapping

**Agent:** Saga the Analyst  
**Output:** `B-Trigger-Map/` (or your configured prefix)

---

## What This Phase Does

User Research connects business goals to user psychology through Trigger Mapping. You discover not just WHO your users are, but WHY they act and WHAT triggers their decisions.

By the end, you'll have a Trigger Map that visually shows how user success drives business success.

---

## What You'll Create

Your Trigger Map includes:

- **Business Goals** - What success looks like for your organization
- **Target Groups** - User types who can help achieve those goals
- **Personas** - Detailed profiles with psychological depth
- **Usage Goals** - What users want vs. what they fear
- **Visual Trigger Map** - Diagram connecting all the pieces
- **Priority Rankings** - Which goals, users, and drivers matter most
- **Feature Impact Analysis** - Scored feature list ranked by strategic value

---

## From Effect Mapping to Trigger Mapping

WDS Trigger Mapping is based on the groundbreaking **Effect Management** methodology from inUse, Sweden.

### Credits & Foundation

**Effect Management** was created by **Mijo Balic** and **Ingrid Domingues (Ottersten)** at **inUse**, Sweden. Their pioneering work on connecting business goals to user behavior through visual mapping - the **Effect Map** - laid the foundation for how we think about strategic software design.

The methodology gained wider recognition through Gojko Adzic's book **"Impact Mapping: Making a Big Impact with Software Products and Projects"** (2012), which acknowledges Effect Mapping as a key influence.

> **Founder's Note:** I personally acquired the insights about the power of the Effect Map back in 2007, and it has served as the philosophical basis for all of my work in UX for almost 20 years. I am eternally grateful for this model that I now have the pleasure to share with the world in an updated version suitable for modern projects.
> — _Martin Eriksson, WDS Creator_

📚 **Further Reading:**

- [Impact Mapping on Amazon](https://www.amazon.com/Impact-Mapping-Software-Products-Projects/dp/0955683645) - Gojko Adzic's book building on Effect Mapping concepts
- [impactmapping.org](https://www.impactmapping.org) - Resources and community

### What is Effect Mapping?

Effect Mapping is the original model that connects business goals to user behavior through a visual map. It includes business goals, target groups, usage goals, and the specific actions/features that enable those goals.

### What is Trigger Mapping?

Trigger Mapping is WDS's adaptation of Effect Mapping, designed for longer shelf life and deeper psychological insight:

**Simplified:**

- Leaves out actions/features from the map
- Focuses on the strategic connections
- Map stays relevant even as features evolve

**Enhanced:**

- Adds **negative driving forces** (fears, frustrations)
- Creates fuller picture of user psychology
- Both what users want AND what they want to avoid

### The Core Insight

Any software is about **flow of value**. There's always a group of people who, through their use of the software, make your success happen.

These users have their own goals:

- **GAIN** - Benefits and positive outcomes they achieve
- **PAIN** - Resistance and friction they experience

**The key:** Make GAIN > PAIN for users, so through their usage, they add value to your system.

### The Four-Layer Structure

The Trigger Map flows horizontally (left to right) in four layers:

**Visual Flow:**
```
Business Goals → Product/Solution → Target Groups → Usage Goals
                                                     (Positive + Negative)
```

**The Layers:**

1. **Business Goals** (Left) - YOUR WHY
   - Vision statement(s) - inspirational direction
   - SMART objectives - measurable targets
   - Multiple goals can feed into the product

2. **Product/Solution** (Center) - WHAT YOU'RE BUILDING
   - Product name and description
   - Central hub connecting goals to users
   - What the product does

3. **Target Groups** (Middle-Right) - THE WHO
   - Prioritized personas (Primary 👥, Secondary 👤)
   - User types whose success drives your success
   - Detailed psychological profiles

4. **Usage Goals** (Right) - THEIR WHY
   - **Positive Drivers** (✅ green) - What they want to achieve
   - **Negative Drivers** (❌ red) - What they want to avoid
   - Separated into distinct groups per target group
   - Both types equally important for design

**Strategic Guidance:**

When all levels are prioritized, you have perfect guidance for design:

- Present features that add value to your most prioritized goal first
- To the highest prioritized target group
- In a way that best suits their most prioritized usage goal
- Make sound decisions about priority of bugs or features based on the total impact on users' goals

---

## How It Works

### Stage 1: Business Goals (15-20 minutes)

Starting question: "Looking at your product brief, what does 'winning' look like for your organization?"

**Understanding Business Goals vs. Metrics**

Business goals are **visionary aspirations** - what you want the business to BE, not metrics you want to hit. These are desirable, exciting outcomes that fill you with purpose.

**Common Business Goals:**
- **Be profitable** - Financially healthy, sustainable
- **Happy customers** - Satisfied, loyal, returning
- **Constant customer flow** - Sustainable demand, steady growth
- **Work smarter** - Reduce costs, less administrative burden, focus on craft
- **Market leadership** - Recognized authority, trusted brand

Each visionary goal is then **measured using the SMART framework**:

**Example Structure:**
```
Business Goal: Be profitable (visionary aspiration)
  └─ Measured by: 25% profit margin, €150K revenue by Q4 2026

Business Goal: Happy customers (visionary aspiration)
  └─ Measured by: Maintain 4.8+ rating, 70% repeat customer rate, NPS 60+

Business Goal: Constant customer flow (visionary aspiration)
  └─ Measured by: 50 new customers per month, page 1 search ranking for key terms
```

**Critical Distinction:**
- ❌ Don't say: "Business Goal: Reduce phone calls 40%" (this is a metric, not aspirational)
- ✅ Do say: "Business Goal: Work smarter → Measured by: 40% reduction in repetitive info calls"

**You'll define:**
- **3 visionary business goals** (what winning looks like) - sometimes 4-5 if truly necessary
- **3 objectives per goal** (how you track progress) - sometimes 4-5 if truly necessary

**The 3×3 Structure:**

Trigger Maps use a focused structure: **3 goals × 3 objectives = 9 total measurements**

```
Goal 1: [Visionary Aspiration]
  Objective 1.1: [Specific, measurable]
  Objective 1.2: [Specific, measurable]
  Objective 1.3: [Specific, measurable]

Goal 2: [Visionary Aspiration]
  Objective 2.1: [Specific, measurable]
  Objective 2.2: [Specific, measurable]
  Objective 2.3: [Specific, measurable]

Goal 3: [Visionary Aspiration]
  Objective 3.1: [Specific, measurable]
  Objective 3.2: [Specific, measurable]
  Objective 3.3: [Specific, measurable]
```

**Why this structure:**
- **Focus:** Forces hard prioritization - what are the 3 MOST important goals?
- **Clarity:** Each goal has clear, measurable progress indicators
- **Flexibility:** Can expand to 4-5 if truly necessary, but default is 3×3

**Hierarchical Ordering:**

Goals should be ordered by strategic priority:

1. **Primary Outcome Goal** - The ultimate business success (e.g., "Become more profitable")
2. **Prerequisite Goals** - What enables the primary goal (e.g., "Get happier customers", "Work smarter")

The order itself signals priority - no need for explicit labels like "(PRIMARY)". If Goal 1 is listed first, it's the most important.

**Objective Alignment:**

Each objective must align with its parent goal:

- **Profitability objectives:** Revenue growth, profit margin, market visibility (drives sales)
- **Customer satisfaction objectives:** Ratings, repeat rate, service quality consistency
- **Operational efficiency objectives:** Time savings, cost reduction, work-life balance

**Example: Källa Fordonservice**
```
1. Become More Profitable (PRIMARY OUTCOME)
   1.1: Maintain 20% profit margin annually
   1.2: Grow revenue 10% year-over-year
   1.3: Achieve Page 1 ranking (visibility drives revenue)

2. Get Happier Customers (PREREQUISITE - enables profitability through loyalty)
   2.1: Maintain 4.8+ Google rating
   2.2: 70%+ repeat customer rate
   2.3: Service quality consistent year-round

3. Work Smarter (PREREQUISITE - enables profitability through efficiency)
   3.1: Reduce repetitive calls by 40%
   3.2: 70% questions answered by website
   3.3: Healthy work-life balance maintained
```

Notice how:
- Goal 1 is the ultimate outcome (profitability)
- Goals 2 & 3 enable Goal 1 (customer loyalty + operational efficiency → profitability)
- Each objective clearly belongs under its parent goal

### Stage 2: Target Groups (20-30 minutes)

Key question: "Who needs to succeed for YOU to succeed?"

Instead of demographics, you discover:

- User types who can drive business success
- The role each type plays in your strategy
- How different users contribute differently
- Why each user type matters to business goals

Users become strategic assets, not just audience segments.

### Stage 3: Psychological Deep Dive (30-40 minutes)

For each user type:

"When this user type is at their best - when they're succeeding - what are they accomplishing? What are they feeling?"

"Now the flip side: What do they desperately want to avoid? What would feel like failure?"

This reveals:

- **Positive Triggers** - What motivates action (wishes, aspirations)
- **Negative Triggers** - What prevents engagement (fears, frustrations)
- **Emotional Drivers** - The psychology behind decisions
- **Behavioral Patterns** - When and why they act

**Understanding Usage Goals vs. Context:**

Usage goals are **contextual** - they activate based on the specific usage situation:

**Example: Golfer at Dubai Golf Resort**

A golfer is a person with many life roles, but in the context of booking a golf range, only their golf-related goals matter:

*Usage goals (in golf booking context):*
- Wish to improve their swing
- Wish to enjoy premium facilities
- Fear of wasting money on low-quality experience

*Other life goals (out of scope):*
- Their parenting goals don't matter here
- Their career ambitions are irrelevant
- Their financial planning is separate

**Why This Matters:**

The same person has different active goals in different contexts. A golf resort's Trigger Map focuses on the usage situation it serves, not the person's entire life.

**Cross-Context Opportunities:**

Sometimes multiple contexts can overlap strategically:

*Example: Golf Resort with Restaurant*

- **Golf Booking Context:** Golfer wants premium experience
- **Restaurant Context:** Same golfer is now hungry after playing
- **Value Chain Opportunity:** "35% restaurant booking rate - Provide golfers with free drink - Golfer - Want to feel taken care of / Not leave hungry"

The person is the same, but their **active goals shift** with the context. Smart businesses can create value chains across contexts.

**Writing Good Driving Forces: WHAT + WHY + WHEN Pattern**

Good driving forces are specific, contextual, and actionable. Use this pattern:

**[WHAT they want/fear] + [WHY it matters] + [WHEN/CONTEXT]**

**✅ Good Examples:**

- "Find immediate reassurance of capability within 30 seconds" (WHAT: reassurance, WHY: stressed/urgent, WHEN: searching on phone)
- "Confirm specialized capability before calling" (WHAT: capability check, WHY: avoid wasted call, WHEN: planning seasonal service)
- "Validate loyalty choice when showing website to others" (WHAT: validation, WHY: justify decision, WHEN: referral context)

**❌ Too Vague:**

- "Want convenience" → Too generic
- "Want peace of mind" → What creates it?
- "Want good experience" → What does "good" mean?

**Test Your Driving Force:**
1. Can a designer create a specific feature to address this?
2. Does it reveal psychology beyond "wants it to work well"?
3. Is it clear WHEN this force is active?

If no to any question, add more specificity.

### Stage 4: Visual Strategy Map (15-20 minutes)

Saga helps build the complete trigger map:

- Connecting every user insight to business goals
- Creating the visual strategy guide
- Validating the strategic logic together

### Stage 5: Prioritization (20-30 minutes)

This stage is critical for shaping the final product concept. You systematically prioritize each column of the Trigger Map.

**The Prioritization Process:**

1. **Rank Business Goals** - Which goal matters most right now? Which is secondary?
2. **Rank Target Groups** - Which user types have the most impact on your top goal?
3. **Rank Usage Goals** - For your top users, which driving forces are most urgent?

**Why This Matters:**

Different prioritizations lead to fundamentally different products. The same Trigger Map can produce wildly different concepts depending on what you prioritize first.

### Stage 6: Feature Impact Analysis (20-30 minutes)

Now the magic happens. You connect strategy to concrete features using a systematic impact scoring approach.

**The Process:**

1. **Gather Feature Ideas** - Pull from your Product Brief, stakeholder input, and brainstorming
2. **Map to Target Groups** - For each feature, identify which target groups it serves
3. **Map to Driving Forces** - Which positive and negative drivers does it address?
4. **Score the Impact** - Features serving multiple groups and drivers score higher

**The Scoring System:** _(Beta - refinements welcome)_

For each feature, award points:

| Impact                                       | Points   |
| -------------------------------------------- | -------- |
| Serves Priority 1 Target Group               | +3       |
| Serves Priority 2 Target Group               | +2       |
| Serves Priority 3 Target Group               | +1       |
| Addresses Priority 1 Positive Driver         | +3       |
| Addresses Priority 2 Positive Driver         | +2       |
| Addresses Priority 3 Positive Driver         | +1       |
| **Addresses Priority 1 Negative Driver**     | **+4**   |
| **Addresses Priority 2 Negative Driver**     | **+3**   |
| **Addresses Priority 3 Negative Driver**     | **+2**   |
| Serves multiple target groups                | +2 bonus |
| Addresses both positive AND negative drivers | +2 bonus |

> **Why negative drivers score higher:** Loss aversion is a well-documented psychological principle - humans work harder to avoid pain than to pursue gain. Features that remove friction, fear, or frustration create stronger user loyalty than features that simply add benefits.

**Example:**

| Feature           | Target Groups                     | Driving Forces                                                                    | Score  |
| ----------------- | --------------------------------- | --------------------------------------------------------------------------------- | ------ |
| One-click booking | P1 Dog Owner (+3), P2 Walker (+2) | Convenience (+3), Fear of complexity (-P1: +4), Multi-group (+2), Both types (+2) | **16** |
| Review system     | P1 Dog Owner (+3)                 | Trust (+2), Fear of bad walker (-P1: +4), Both types (+2)                         | **11** |
| Calendar sync     | P2 Walker (+2)                    | Efficiency (+1)                                                                   | **3**  |

**The Output:**

A ranked feature list showing:

- Which features have the broadest impact
- Which features are "single-purpose" vs "multi-impact"
- Natural MVP candidates (highest scores)
- Features to defer (low scores but still valuable)

**Why This Works:**

Features that resonate with multiple target groups and address multiple driving forces are inherently more valuable. They create more value per development effort and satisfy more users simultaneously.

---

## Personas with Depth

Traditional personas describe demographics: "Jennifer, 34, likes yoga and lattes."

WDS personas capture psychology:

**Alliterative Naming** - Each persona gets a memorable name that hints at their role:

- "Patrick the Professional" - Decision-maker focused on efficiency
- "Sophie the Socializer" - Values connection and community
- "Tyler the Technical" - Wants control and customization

**What Each Persona Includes:**

- Role and context
- Goals they're trying to achieve
- Fears and frustrations
- How they'd describe their problem
- What success looks like to them
- Triggers that motivate action

---

## When to Use This Phase

**Use after Phase 1 if:**

- Building a new product
- Need clarity on who you're building for
- Want design decisions grounded in user psychology

**Start here if:**

- You have product vision but unclear user strategy
- Existing personas feel shallow or unused
- Features aren't connecting with users

**Skip if:**

- Quick enhancement to existing feature
- Users are already well-documented and validated
- Design system work without new user research

---

## What to Prepare

Bring:

- Your completed Product Brief (Phase 1)
- Any existing user research (even informal)
- Stakeholder availability for the workshop

---

## What Comes Next

Your Trigger Map enables:

- **Phase 3: Requirements** - Technical decisions aligned with user priorities
- **Phase 4: UX Design** - Design work grounded in user psychology
- **Development priorities** - Clear guidance on what to build first

The trigger map becomes the strategic brain of your product.

---

## Tips for Great Sessions

**Think strategically, not demographically**

- "Who needs to win for us to win?" not "Who might use this?"
- Connect every user insight to business outcomes

**Go deep on psychology**

- Push beyond surface responses
- Ask "why" multiple times
- Understand motivations, not just behaviors

**Build the map live**

- See connections as they emerge
- Validate strategic logic together
- Make it visual and shareable

---

## Example Output

See: `examples/dog-week-patterns/B-Trigger-Map/` for a complete Trigger Map with personas from a real project.

---

## Related Resources

**Method Guides:**
- [Value Trigger Chain Guide](./value-trigger-chain-guide.md) - Extracting VTCs from Trigger Map
- [Phase 1: Product Exploration](./phase-1-product-exploration-guide.md) - Strategic foundation (prerequisite)
- [Phase 4: UX Design Guide](./phase-4-ux-design-guide.md) - Using Trigger Map in scenarios

**Foundational Models:**
- [Impact/Effect Mapping](../models/impact-effect-mapping.md) - The foundational methodology Trigger Mapping derives from
- [Customer Awareness Cycle](../models/customer-awareness-cycle.md) - Understanding user awareness stages

**Workflows:**
- Trigger Mapping Workflow: `workflows/2-trigger-mapping/` (see workflow files)

---

_Phase 2 of the Whiteport Design Studio method_
