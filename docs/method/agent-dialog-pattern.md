# Agent Dialog Pattern

**Status:** Core WDS Pattern
**Created:** 2026-02-11
**Applies to:** All WDS workflows

---

## The Problem

In BMad workflows, agents ask questions and generate documents. But the **conversation itself was lost**:

- Questions and answers disappeared after completion
- Reasoning behind decisions was not captured
- Resuming work required starting from scratch
- Next agents had no context from previous sessions
- Learning from past projects was difficult

**Result:** Knowledge was trapped in documents without the "why" behind them.

---

## The Solution: Agent Dialog as First-Class Artifact

Every significant workflow creates an **agent dialog** that logs:

1. Every question asked
2. Every answer given
3. Which documents each answer populated
4. Key decisions and reasoning
5. Progress status
6. What's next

**The agent dialog IS the design process**, documented in real-time.

---

## When to Create Agent Dialogs

**Create an agent dialog when:**

✅ Starting a new WDS phase (Phase 0, 1, 2, etc.)
✅ Running a discovery/research workflow
✅ Making architectural or strategic decisions
✅ Creating multiple related documents
✅ Work that will take multiple sessions
✅ Anything where "why we decided X" matters

**Don't create for:**

❌ Quick fixes (typo corrections, small edits)
❌ Single-purpose tasks (just updating one section)
❌ Trivial operations (file renaming, formatting)

**Rule of thumb:** If someone returning tomorrow would ask "what did you do and why?", create an agent dialog.

---

## Standard Format

Location: `design-process/progress/agent-dialogs/{date}-{workflow-name}.md`

```markdown
# [Workflow Name]: [Project Name]

**Workflow:** [Phase/Task]
**Project:** [Project Name]
**Date:** YYYY-MM-DD
**Status:** in_progress | complete | paused | abandoned
**Agent:** [Agent Name]
**Session:** [1, 2, 3... if multi-session]

---

## Context

[Why this workflow started, what preceded it, relevant background]

---

## Questions & Answers

### [Topic/Section Name]
**Q:** [Question text]
**A:** [User's answer]
**Documented in:** [file.md (section), file2.md (section)]
**Decision:** [If a key decision was made, note it here]
**Timestamp:** HH:MM

### [Next Topic]
**Q:** [Question]
**A:** [Answer]
**Documented in:** [files]

---

## Key Decisions

- **[Decision 1]:** [What was decided] — [Why/rationale]
- **[Decision 2]:** [What was decided] — [Why/rationale]

---

## Progress Status

- [x] Section 1: [Name]
- [x] Section 2: [Name]
- [ ] Section 3: [Name] (in progress)
- [ ] Section 4: [Name]

---

## Generated Artifacts

- [x] [file1.md] — [Brief description]
- [x] [file2.md] — [Brief description]
- [ ] [file3.md] — In progress

---

## Blockers / Issues

[Any blockers encountered, unresolved questions, things to revisit]

---

## Next Steps

[What should happen after this workflow completes]

---

**Status:** [current status]
**Last Updated:** YYYY-MM-DD HH:MM
```

---

## Agent Responsibilities

### On Workflow Start

1. **Create agent dialog file**
   - Name: `YYYY-MM-DD-{workflow-slug}.md`
   - Location: `design-process/progress/agent-dialogs/`
   - Status: `in_progress`

2. **Explain to user**
   ```
   "I'm creating an agent dialog to track our conversation.
    This helps us resume if interrupted and documents decisions."
   ```

3. **Initialize open documents**
   - List which documents will be created/updated
   - Open them for progressive documentation

### During Workflow

1. **Log every Q&A**
   - Question asked
   - Answer received
   - Where it was documented
   - Timestamp (if multi-hour session)

2. **Show confirmations**
   ```
   "✓ Added to platform-requirements.md (Core Platform section)"
   ```

3. **Update progress status**
   - Mark sections complete as you go
   - Update artifact list with generated files

4. **Document decisions**
   - When a key decision is made, note it explicitly
   - Capture the reasoning, not just the outcome

### On Workflow Complete

1. **Update dialog status**
   - Status: `complete`
   - Last Updated: timestamp
   - Summary of key outcomes

2. **Link from design-log.md**
   ```markdown
   ## 2026-02-11 - Phase 1 Complete

   [Summary of what happened]

   **Full details:** See [agent dialog](./agent-dialogs/2026-02-11-phase-1-discovery.md)
   ```

3. **Update project outline**
   - Mark phase complete
   - List generated artifacts
   - Reference agent dialog

### On Workflow Pause/Resume

**On Pause:**
1. Update status to `paused`
2. Note where you left off
3. Document any blockers

**On Resume:**
1. Read previous dialog
2. Show user summary: "Here's where we left off..."
3. Continue from last section
4. Update session number if helpful

---

## Benefits

### 1. Resumable Sessions
```
Session interrupted → Agent dialog shows progress
Next agent reads dialog → Continues exactly where left off
```

### 2. Context for Next Phase
```
Phase 2 agent reads Phase 1 dialog
Understands decisions made, constraints chosen
Builds on previous work with full context
```

### 3. Audit Trail
```
Client: "Why did we decide X?"
You: "Phase 1 dialog, Section 3 — here's what you said"
```

### 4. Knowledge Transfer
```
New team member reads dialogs
Understands reasoning, not just outcomes
Can continue work with confidence
```

### 5. Quality Assurance
```
Review dialogs to ensure:
- All questions asked
- Decisions documented
- Nothing missed
```

### 6. Learning & Improvement
```
Read past dialogs to:
- Learn question patterns
- Understand decision quality
- Improve process
```

---

## Relationship to Other Files

```
design-process/progress/
├── wds-project-outline.yaml    # Config & status
├── design-log.md                # Executive summary
└── agent-dialogs/               # Detailed transcripts
    ├── 2026-02-10-phase-0.md
    └── 2026-02-11-phase-1.md
```

**Hierarchy:**
- **Outline:** Configuration and phase status (machine-readable)
- **Design log:** High-level summary of what happened (executive summary)
- **Agent dialogs:** Full transcripts of how it happened (detailed record)

**Use cases:**
- Quick status check → Read outline
- Understand key decisions → Read design log
- Resume work / understand reasoning → Read agent dialog

---

## Implementation Checklist

For any workflow implementation:

- [ ] Create agent dialog on workflow start
- [ ] Log all questions and answers
- [ ] Note which documents each answer populates
- [ ] Track progress status
- [ ] Document key decisions with reasoning
- [ ] Update status on completion/pause
- [ ] Link from design-log.md
- [ ] Update project outline

---

## Examples

See:
- `kalla-fordonsservice/design-process/progress/agent-dialogs/` (reference implementation)
- Template: `docs/templates/agent-dialog.template.md`

---

## Why This Matters

**The conversation IS the design process.**

By documenting the conversation, we preserve:
- The questions that led to insights
- The reasoning behind decisions
- The context future agents need
- The knowledge that makes projects resumable

Agent dialogs make BMad/WDS truly collaborative across sessions and agents.

---

_Pattern established: 2026-02-11_
_First implementation: Källa Fordonservice Phase 1_
