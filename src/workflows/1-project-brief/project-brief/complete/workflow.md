---
name: Product Brief Workflow
description: Create comprehensive product briefs through collaborative step-by-step discovery
web_bundle: true
---

# Product Brief Workflow

**Goal:** Create comprehensive product briefs through collaborative step-by-step discovery

**Your Role:** Work as equals with the user - you bring structured thinking and facilitation skills, they bring domain expertise and product vision.

---

## WORKFLOW ARCHITECTURE

This uses **step-file architecture** for disciplined execution:

### Core Principles

- **Micro-file Design**: Each step is a self contained instruction file that is a part of an overall workflow that must be followed exactly
- **Just-In-Time Loading**: Only current step file is in memory - never load future step files until told to do so
- **Sequential Enforcement**: Sequence within step files must be completed in order, no skipping or optimization allowed
- **State Tracking**: Document progress in output file frontmatter using `stepsCompleted` array when a workflow produces a document
- **Append-Only Building**: Build documents by appending content as directed to output file

### Step Processing Rules

1. **READ COMPLETELY**: Always read entire step file before taking any action
2. **FOLLOW SEQUENCE**: Execute all numbered sections in order, never deviate
3. **WAIT FOR INPUT**: If a menu is presented, halt and wait for user selection
4. **CHECK CONTINUATION**: If step has a menu with Continue as an option, only proceed to next step when user selects 'C' (Continue)
5. **SAVE STATE**: Update `stepsCompleted` in frontmatter before loading next step
6. **LOAD NEXT**: When directed, load, read entire file, then execute next step file

### Critical Rules (NO EXCEPTIONS)

- 🛑 **NEVER** load multiple step files simultaneously
- 📖 **ALWAYS** read entire step file before execution
- 🚫 **NEVER** skip steps or optimize the sequence
- 💾 **ALWAYS** update frontmatter of output files when writing final output for a specific step
- 🎯 **ALWAYS** follow the exact instructions in step file
- ⏸️ **ALWAYS** halt at menus and wait for user input
- 📋 **NEVER** create mental todo lists from future steps

---

## AGENT DIALOG INTEGRATION

This workflow creates and maintains an **agent dialog** to track the conversation and decisions.

### Purpose

Agent dialogs provide:
- Full conversation history (questions asked, answers given)
- Context for resuming if interrupted
- Documentation of "why" behind decisions
- Audit trail for future reference
- Handoff context for next workflow phases

### On Workflow Start (Before Step 1)

**1. Create agent dialog file:**
```
Location: {output_folder}/progress/agent-dialogs/{date}-product-brief.md
Template: {project-root}/{bmad_folder}/wds/templates/agent-dialog.template.md
```

**2. Initialize with:**
- **Workflow:** Phase 1 - Product Brief (Complete)
- **Project:** {project_name}
- **Status:** in_progress
- **Context:** "Creating comprehensive product brief through collaborative discovery"
- **Plan:** List the 12 steps to be completed

**3. Inform user:**
> "I'm creating an agent dialog to track our conversation. This helps us resume if interrupted and documents decisions."

### During Each Step

After completing each step's work and before loading the next step, update the agent dialog with:

```markdown
### [Step Name]
**Q:** [Key questions asked]
**A:** [User responses - summarized]
**Documented in:** product-brief.md ([section name])
**Key insights:** [Any important revelations or decisions]
**Status:** Complete
**Timestamp:** [HH:MM]
```

### On Workflow Complete

**1. Update agent dialog:**
- Status: `complete`
- Last Updated: timestamp
- Mark all sections complete in Progress Status
- List final artifact in Generated Artifacts

**2. Note what's next:**
- "Ready for Content & Language, Platform Requirements, and Visual Direction workflows"

---

## INITIALIZATION SEQUENCE

### 1. Configuration Loading

Load and read full config from {project-root}/{bmad_folder}/wds/config.yaml and resolve:

- `project_name`, `output_folder`, `user_name`, `communication_language`, `document_output_language`, `user_skill_level`

### 2. Agent Dialog Creation

Create agent dialog file following the AGENT DIALOG INTEGRATION instructions above.

### 3. First Step EXECUTION

Load, read full file and then execute `{project-root}/{bmad_folder}/wds/workflows/1-project-brief/project-brief/complete/steps-c/step-01-init.md` to begin workflow.

**Note:** Alignment & Signoff is now a separate, optional workflow. If you need stakeholder approval before starting, use the alignment & signoff workflow first: `{project-root}/{bmad_folder}/wds/workflows/1-project-brief/alignment-signoff/workflow.md`
