# Step 03: Generate Persona Documents

**Goal:** Create detailed persona profiles for each target user group

---

## Purpose

For EACH persona (Primary, Secondary, Tertiary), create a comprehensive document with:
- Rich background and context
- Current situation and challenges
- Psychological profile
- Complete driving forces (6 total: 3 wants, 3 fears)
- Transformation journey
- Strategic role and impact

---

## Input Required

From trigger map YAML:
- `targetGroups` section with Primary, Secondary, and optional Tertiary personas
- Each target group has: name, role, type, roleInFlywheel, and 6 drivingForces (3 wants, 3 fears)

---

## Template Reference

Use the comprehensive persona document template:
`templates/persona-document-template.md`

This template provides the complete structure for sections 1-13 of each persona document.

---

## File Naming Convention

```
02-[Name]-the-[Role].md  → Primary persona
03-[Name]-the-[Role].md  → Secondary persona
04-[Name]-the-[Role].md  → Tertiary persona (if exists)
```

**Examples:**
- `02-Sarah-the-Student.md`
- `03-Marcus-the-Mentor.md`
- `04-Emma-the-Enthusiast.md`

---

## Generation Order

Generate persona documents in this specific order:

1. **PRIMARY persona FIRST** (most detail, full transformation)
2. **SECONDARY persona SECOND** (validation focus)
3. **TERTIARY persona THIRD** (benefits focus, optional)

---

## Key Requirements

**Length:** Each persona should be ~250-375 lines

**Tone:**
- Rich, nuanced, human
- Not "converting" but "creating awesome"
- Natural language, storytelling

**Driving Forces:**
- Each must have **[Product] Promise** or **[Product] Answer**
- Show how product addresses each driver
- Be specific and actionable

**Transformation:**
- PRIMARY persona gets full BEFORE/AFTER section
- Show emotional journey, not just functional
- Use emojis to show emotional states

**Strategic Triangle:**
- Show how personas interconnect
- Explain the loop/flywheel
- Make relationships clear

---

## Persona Type-Specific Sections

### For PRIMARY Persona

Include section: **"Role in Flywheel: Creating Awesome [Personas] Who Become [Champions]"**
- Show the natural evolution
- Explain what they need to see on product page
- Focus on transformation and champion creation

### For SECONDARY Persona

Include section: **"Validation Strategy"**
- What they need to see about the product
- Conversion path (Discovery → Evaluation → Adoption → Advocacy)
- Focus on validation and trust

### For TERTIARY Persona

Include section: **"How [Persona Name] Discovers [Product] Value"**
- The recognition path
- Experience → Recognition → Appreciation → Word of Mouth
- Focus on benefits and discovery

---

## Examples

Reference examples:
- `examples/WDS-Presentation/docs/2-trigger-map/02-Stina-the-Strategist.md` (PRIMARY - 282 lines)
- `examples/WDS-Presentation/docs/2-trigger-map/03-Lars-the-Leader.md` (SECONDARY - 316 lines)
- `examples/WDS-Presentation/docs/2-trigger-map/04-Felix-the-Full-Stack.md` (TERTIARY - 375 lines)

---

## Output

Generate and save persona documents:
- `02-[Name]-the-[Role].md` (Primary)
- `03-[Name]-the-[Role].md` (Secondary)
- `04-[Name]-the-[Role].md` (Tertiary, if exists)

<output>✅ All persona documents created!</output>

---

## Next Step

<output>Ready for Step 4: Generate Key Insights Document</output>

<action>Load and execute: step-04-generate-key-insights.md</action>

Do NOT skip ahead.
