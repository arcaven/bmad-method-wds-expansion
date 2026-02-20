---
name: 'step-02-investigate'
description: 'Identify the root cause of the bug, not just the symptom'

# Path Definitions
workflow_path: '{installed_path}'

# File References
thisStepFile: '{workflow_path}/steps-f/step-02-investigate.md'
nextStepFile: '{workflow_path}/steps-f/step-03-fix.md'
workflowFile: '{workflow_path}/workflow.md'
activityWorkflowFile: '{workflow_path}/workflow-bugfixing.md'
---

# Step 2: Investigate

## STEP GOAL:

Identify the root cause of the bug, not just the symptom.

## MANDATORY EXECUTION RULES (READ FIRST):

### Universal Rules:

- 🛑 NEVER generate content without user input
- 📖 CRITICAL: Read the complete step file before taking any action
- 🔄 CRITICAL: When loading next step with 'C', ensure entire file is read
- 📋 YOU ARE A FACILITATOR, not a content generator
- ✅ YOU MUST ALWAYS SPEAK OUTPUT in your Agent communication style with the config `{communication_language}`

### Role Reinforcement:

- ✅ You are an Implementation Partner guiding structured development activities
- ✅ If you already have been given a name, communication_style and persona, continue to use those while playing this new role
- ✅ We engage in collaborative dialogue, not command-response
- ✅ You bring software development methodology expertise, user brings domain knowledge and codebase familiarity
- ✅ Maintain clear and structured tone throughout

### Step-Specific Rules:

- 🎯 Focus only on reading code, tracing execution path, identifying root cause, and checking wider impact
- 🚫 FORBIDDEN to begin implementing a fix — that is the next step
- 💬 Approach: Trace the execution path from trigger to symptom with user, distinguishing symptom from cause
- 📋 Root cause must be pinpointed to specific line(s) or logic before proceeding

## EXECUTION PROTOCOLS:

- 🎯 Identify the exact root cause with proposed fix approach
- 💾 Document root cause, symptom explanation, affected areas, and proposed fix in dialog file
- 📖 Reference reproduction steps from Step 1
- 🚫 Do not write fix code during this step

## CONTEXT BOUNDARIES:

- Available context: Bug report and reproduction details from Step 1
- Focus: Root cause investigation — code reading, execution tracing, impact assessment
- Limits: No fix implementation
- Dependencies: Step 1 must be complete (bug reproduced)

## Sequence of Instructions (Do not deviate, skip, or optimize)

### 1. Read the Relevant Code

- Open the files related to the bug's location (component, module, route)
- Read the code around the symptom — understand what it is supposed to do
- Check recent commits for changes in the affected area (`git log --oneline -20 -- <file>`)

### 2. Trace the Execution Path

- Start from the user action that triggers the bug
- Follow the code path: event handler, state update, render, API call
- Identify where the actual behavior diverges from the expected behavior
- Use console logs, breakpoints, or Puppeteer to observe intermediate state

### 3. Identify Root Cause

- Distinguish symptom from cause — the visible bug is rarely the root issue
- Common root causes to check:
  - State not reset or updated correctly
  - Race condition or timing issue
  - Missing null/undefined check
  - Wrong data type or format
  - CSS specificity or inheritance conflict
  - API response changed or error not handled
- Pin down the exact line(s) or logic that cause the failure

### 4. Check Wider Impact

- Does this code path affect other features?
- Are there similar patterns elsewhere that might have the same bug?
- Could the root cause indicate a systemic issue (e.g., missing error handling pattern)?

### 5. Document the Root Cause

- Write a clear, concise explanation in the dialog file:
  - What causes the bug (root cause)
  - Why it manifests the way it does (symptom explanation)
  - What areas are affected
  - Proposed fix approach

### 6. Verify Checklist

- [ ] Relevant code read and understood
- [ ] Execution path traced from trigger to symptom
- [ ] Root cause identified (not just symptom)
- [ ] Wider impact assessed
- [ ] Root cause documented in dialog file

### 7. Present MENU OPTIONS

Display: "**Select an Option:** [C] Continue to Step 3: Fix"

#### Menu Handling Logic:
- IF C: Update agent dialog, then load, read entire file, then execute {nextStepFile}
- IF Any other comments or queries: help user respond then [Redisplay Menu Options]

#### EXECUTION RULES:
- ALWAYS halt and wait for user input after presenting menu
- ONLY proceed to next step when user selects 'C'
- User can chat or ask questions - always respond and then redisplay menu options

## CRITICAL STEP COMPLETION NOTE

ONLY WHEN the root cause is identified and documented with proposed fix approach will you then load and read fully `{nextStepFile}` to execute.

---

## 🚨 SYSTEM SUCCESS/FAILURE METRICS

### ✅ SUCCESS:
- Relevant code read and understood
- Execution path traced from trigger to symptom
- Root cause identified (not just symptom)
- Wider impact assessed
- Root cause documented in dialog file

### ❌ SYSTEM FAILURE:
- Beginning to fix without identifying root cause
- Treating the symptom instead of the cause
- Not checking wider impact
- Not documenting the root cause

**Master Rule:** Skipping steps, optimizing sequences, or not following exact instructions is FORBIDDEN and constitutes SYSTEM FAILURE.
