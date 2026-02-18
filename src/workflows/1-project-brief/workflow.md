---
name: project-brief
description: Establish project context - foundation for all design work
web_bundle: true
---

# Phase 1: Product Brief

**Goal:** Establish the strategic foundation for all design work through collaborative discovery.

**Your Role:** In addition to your name, communication_style, and persona, you are also a Strategic Business Analyst collaborating with the project owner. This is a partnership, not a client-vendor relationship. You bring structured thinking and facilitation skills, while the user brings domain expertise and product vision. Work together as equals.

---

## WORKFLOW ARCHITECTURE

This phase routes to the appropriate brief workflow based on project configuration.

### Brief Level Routing

Load `brief_level` from `{output_folder}/wds-workflow-status.yaml:config.brief_level`:

- **complete** → `{installed_path}/101-project-brief/workflow.md`
- **simplified** → `{installed_path}/102-project-brief-simplified/workflow.md`

### Sub-Workflows

| # | Name | Purpose |
|---|------|---------|
| 100 | [Alignment & Signoff](100-alignment-signoff/workflow.md) | Secure stakeholder alignment before starting (optional, pre-Phase 1) |
| 101 | [Project Brief](101-project-brief/workflow.md) | Full product brief through collaborative step-by-step discovery |
| 102 | [Project Brief Simplified](102-project-brief-simplified/workflow.md) | Quick brief for smaller projects (5-10 minutes) |
| 103 | [Content Language](103-content-language/workflow.md) | Define tone of voice, language strategy, and content guidelines |
| 104 | [Inspiration Analysis](104-inspiration-analysis/workflow.md) | Analyze reference sites to document visual/UX preferences |
| 105 | [Visual Direction](105-visual-direction/workflow.md) | Establish visual style, brand aesthetics, and design direction |
| 106 | [Platform Requirements](106-platform-requirements/workflow.md) | Define technical boundaries and platform decisions |
| 107 | [Handover](107-handover/workflow.md) | Package Phase 1 artifacts for handover to Phase 2 |

---

## INITIALIZATION SEQUENCE

### 1. Configuration Loading

Load and read full config from `{project-root}/_bmad/wds/config.yaml` and resolve:

- `project_name`, `output_folder`, `user_name`, `communication_language`, `document_output_language`
- `brief_level` from `{output_folder}/wds-workflow-status.yaml:config.brief_level`

### 2. Route to Brief Workflow

Based on `brief_level`, load and execute the appropriate sub-workflow.

### Output

- `{output_folder}/A-Product-Brief/project-brief.md`
