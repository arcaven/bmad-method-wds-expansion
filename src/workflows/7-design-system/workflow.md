---
name: design-system
description: Extract and maintain design system components from UX specifications
web_bundle: true
---

# Phase 7: Design System

**Goal:** Extract reusable design system components from UX specifications and maintain a consistent component library.

**Your Role:** Guide the designer through component extraction, similarity analysis, and design system operations. Route new component specifications through assessment before creating or updating design system entries.

---

## WORKFLOW ARCHITECTURE

Optional phase — only active if design system is enabled in the project configuration. Triggered from Phase 4 component specifications.

### Entry Point

The **Design System Router** (`design-system-router.md`) is the primary entry point, routing component specifications to the appropriate operation.

### Sub-Areas

| # | Name | Purpose |
|---|------|---------|
| 700 | [Assessment](700-assessment/) | 7-step similarity analysis for new components |
| 702 | [Operations](702-operations/) | Component CRUD operations (create, update, add variant) |

### Reference Content

- `design-system-guide.md` — Comprehensive design system guide
- `design-system-router.md` — Router logic for component routing
- `templates/` — Component and token templates

### Prerequisites

- Phase 4: UX Design (component specifications required)

---

## INITIALIZATION SEQUENCE

### 1. Configuration Loading

Load and read full config from `{project-root}/_bmad/wds/config.yaml` and resolve:

- `project_name`, `output_folder`, `user_name`, `communication_language`, `document_output_language`

### 2. First Step

Load and execute `design-system-router.md` to route the component specification.

### Output

- `{output_folder}/D-Design-System/components/*.md`
- `{output_folder}/D-Design-System/design-tokens.md`
- `{output_folder}/D-Design-System/component-library-config.md`
