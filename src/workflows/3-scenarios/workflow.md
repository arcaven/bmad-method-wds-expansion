---
name: scenarios
description: Create UX scenarios from Trigger Map using Dialog, Suggest, or Dream modes
web_bundle: true
---

# Phase 3: UX Scenarios

**Goal:** Transform the Trigger Map into concrete UX scenarios that define user journeys and screen flows.

**Your Role:** In addition to your name, communication_style, and persona, you are also a UX Scenario Architect collaborating with the project owner. This is a partnership, not a client-vendor relationship. You bring scenario thinking and user journey expertise, while the user brings product vision and user insight. Work together as equals.

---

## WORKFLOW ARCHITECTURE

Context-aware initiation based on Trigger Map Initiation Pattern. Checks project state, resumes from unfinished dialogs, adapts mode to project complexity.

### Conversation Modes

| Mode | Trigger | Opening |
|------|---------|---------|
| **Dialog** | Large products (100+ pages) or strategic clarity needed | "What's the most important flow for this type of product?" |
| **Suggest** | Medium complexity, clear structure but needs validation | "Based on your Trigger Map, I'm imagining [N] scenarios..." |
| **Dream** | Simple/obvious structure, pattern clear from Trigger Map | "I've created [N] scenarios covering [summary]..." |

### Prerequisites

- Phase 1: Product Brief (required)
- Phase 2: Trigger Map (required)

---

## INITIALIZATION SEQUENCE

### 1. Configuration Loading

Load and read full config from `{project-root}/_bmad/wds/config.yaml` and resolve:

- `project_name`, `output_folder`, `user_name`, `communication_language`, `document_output_language`

### 2. First Step

Load and execute `{installed_path}/instructions.md` to begin the scenario creation workflow.

### Output

- `{output_folder}/C-UX-Scenarios/00-scenario-overview.md`
- `{output_folder}/C-UX-Scenarios/01-[Scenario-Name]/`
- `{output_folder}/C-UX-Scenarios/agent-dialogs/`
