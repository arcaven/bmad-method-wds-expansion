# Step 0.2: Project Configuration & Structure

## CONTEXT

Project type is confirmed (Greenfield or Brownfield). Now we configure the project and create the folder structure.

---

## 1. PROJECT NAME

<ask>
**What's your project name?**

Project name:
</ask>

---

## 2. WHAT ARE YOU BUILDING?

<ask>
**What type of product is this?**

[A] **Landing Page** - Single page, marketing focused
    → Simplified workflow, minimal phases

[B] **Website** - Multiple pages, content focused
    → Standard workflow, most phases

[C] **Web Application** - Complex features, user interactions
    → Full workflow, all phases

[D] **Mobile App** - iOS/Android application
    → Full workflow + platform considerations

Choice:
</ask>

<action>
Store as `product_complexity`:
- A → simple (skip Phase 2, 3, 5)
- B → standard (optional Phase 5)
- C → complex (all phases)
- D → complex (all phases + mobile config)
</action>

---

## 3. TECH STACK (Optional)

<ask>
**Tech stack?** [A] React/Next [B] Vue/Nuxt [C] WordPress [D] HTML [E] Other [F] Skip
</ask>

<action>Store as `tech_stack` (or null if F)</action>

---

## 4. COMPONENT LIBRARY (Optional)

<ask>
**Component library?**

[A] **shadcn/ui** → Skip Phase 5
[B] **Tailwind only** → Phase 5 optional
[C] **Material UI** → Skip Phase 5
[D] **Custom** → Phase 5 recommended
[E] **Skip** - Decide later
</ask>

<action>Store as `component_library`. If A/C → `skip_design_system: true`</action>

---

## 5. ROOT FOLDER NAME

<ask>
**Where should design process files live?**

[A] **design-process** (Recommended)
    - Clear separation from technical docs
    - Professional client presentation
    - Standard Whiteport convention

[B] **docs**
    - Traditional convention
    - May conflict with technical documentation

[C] **Custom name**
    - Specify your own folder name

Choice:
</ask>

<action>
Store as `root_folder`:
- A → design-process (default)
- B → docs
- C → Ask for custom name, then store

Default if skipped: design-process
</action>

---

## 6. BRIEF LEVEL

<action if="greenfield">
**Greenfield projects always use Complete Brief.**

Store `brief_level: complete`

(No question needed — greenfield means we're building something new and need full strategic foundation.)
</action>

<ask if="brownfield">
**How thorough should the Project Brief be?**

[A] **Complete**
    - Full strategic documentation
    - Reverse-engineer vision, users, competitive landscape
    - Best for: Major redesigns, new team members, unclear direction

[B] **Simplified** (Recommended for brownfield)
    - Document what exists + what you want to change
    - Quick context capture
    - Best for: Focused improvements, clear goals

Choice:
</ask>

<action>Store as `brief_level`: complete | simplified</action>

---

## 7. STRATEGIC ANALYSIS LEVEL (Greenfield only)

<ask if="greenfield AND product_complexity != simple">
**How deep should the user/market analysis go?**

[A] **Full Trigger Map** (Recommended for complex products)
    - Separate Phase 2 workflow
    - Deep persona development
    - Feature Impact Analysis
    - Customer awareness stages
    - Best for: Products with multiple user types, B2B, marketplaces

[B] **Simplified VTC** (Value Trigger Chain)
    - Embedded in Project Brief
    - Core value proposition + key triggers
    - Basic persona sketch
    - Best for: Single user type, clear target market, MVPs

[C] **Skip** (Not recommended)
    - No formal user analysis
    - Jump straight to design
    - Best for: Internal tools, personal projects

Choice:
</ask>

<action>
Store as `strategic_analysis`:
- A → full (Phase 2 enabled)
- B → simplified (VTC in Phase 1, skip Phase 2)
- C → skip (skip Phase 2)
</action>

---

## 8. CREATE STRUCTURE & OUTLINE

<action>
**Check existing:** Look for `{{root_folder}}/` and `{{root_folder}}/progress/wds-project-outline.yaml`
**If exists:** Ask to keep or reset

**Create folder structure:**

1. **Create root folder:** `{{root_folder}}/`
2. **Create progress folder:** `{{root_folder}}/progress/`
3. **Create phase folders:**
   - Greenfield: `{{root_folder}}/A-Product-Brief/`, `B-Trigger-Map/`, `C-Platform-Requirements/`, `D-UX-Scenarios/`, `E-Design-System/`, `F-PRD/`, `G-Testing/`
   - Brownfield: `{{root_folder}}/A-Product-Brief/`, `improvements/`, `deliveries/`

**Generate `{{root_folder}}/progress/wds-project-outline.yaml`:**

```yaml
# WDS Project Outline
# Generated: {{date}}
# Location: {{root_folder}}/progress/wds-project-outline.yaml

project:
  name: "{{project_name}}"
  type: {{greenfield|brownfield}}
  created: "{{date}}"
  description: "{{brief_description}}"

config:
  root_folder: "{{root_folder}}"  # design-process | docs | custom
  product_complexity: {{simple|standard|complex}}
  tech_stack: {{tech_stack|null}}
  component_library: {{component_library|null}}
  brief_level: {{complete|simplified}}
  strategic_analysis: {{full|simplified|skip}}
  skip_design_system: {{true|false}}
  skip_trigger_map: {{true|false}}

folders:
  product_brief: "{{root_folder}}/A-Product-Brief"
  trigger_map: "{{root_folder}}/B-Trigger-Map"
  platform_requirements: "{{root_folder}}/C-Platform-Requirements"
  scenarios: "{{root_folder}}/D-UX-Scenarios"
  design_system: "{{root_folder}}/E-Design-System"
  prd: "{{root_folder}}/F-PRD"
  testing: "{{root_folder}}/G-Testing"

phases:
  {{generated_phases}}
```
</action>

**Generate `{{root_folder}}/progress/design-log.md`:**

```markdown
# Design Process Log

Project: {{project_name}}
Started: {{date}}

---

## {{date}} - Project Initialized (Phase 0)

**Configuration:**
- Type: {{greenfield/brownfield}}
- Complexity: {{product_complexity}}
- Tech Stack: {{tech_stack}}
- Brief Level: {{brief_level}}

**Next Steps:**
- Phase 1: Product Brief
{{#if strategic_analysis == "full"}}
- Phase 2: Trigger Mapping
{{/if}}

---

_Use this log to track major decisions, insights, and progress through the design process._
```

**Create agent dialogs folder:** `{{root_folder}}/progress/agent-dialogs/`

</action>

---

## 9. SUMMARY & NEXT STEPS

<output>
**Project configured!**

| Setting | Value |
|---------|-------|
| Name | {{project_name}} |
| Type | {{greenfield/brownfield}} |
| Complexity | {{product_complexity}} |
| Brief Level | {{brief_level}} |
| Strategic Analysis | {{strategic_analysis}} |
| Tech Stack | {{tech_stack or "Not set"}} |

**Phases:** {{enabled_phases}} enabled, {{skipped_phases}} skipped

---

**[GREENFIELD]** Ready for Phase 1: Project Brief

{{#if strategic_analysis == "full"}}
→ Full workflow: Phase 1 (Brief) → Phase 2 (Trigger Map) → Phase 3+
{{else if strategic_analysis == "simplified"}}
→ Streamlined: Phase 1 with VTC → Phase 3+ (skip Phase 2)
{{else}}
→ Direct: Phase 1 minimal → Phase 4 (UX Design)
{{/if}}

[A] Start Phase 1 now
[B] Hand off to Saga (specialist)

**[BROWNFIELD]** Ready for Phase 8: Existing Product

[A] Create Limited Brief now
[B] Scan my codebase first
[C] I know what to improve - go
</output>

---

## 10. ROUTING

<action>
**Greenfield:**
- [A] → Phase 1 workflow (brief_level + strategic_analysis determines path)
- [B] → Hand off to Saga

**Brownfield:**
- [A] → Load Limited Brief template
- [B] → Scan codebase, then brief
- [C] → Phase 8.1 Identify Opportunity
</action>

---

_Phase 0: Project Setup — Step 0.2: Configuration & Structure_
