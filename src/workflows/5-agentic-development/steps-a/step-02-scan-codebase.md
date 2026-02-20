---
name: 'step-02-scan-codebase'
description: 'Build a mental model of the codebase through systematic exploration of structure, tech stack, and entry points'

# Path Definitions
workflow_path: '{installed_path}'

# File References
thisStepFile: '{workflow_path}/steps-a/step-02-scan-codebase.md'
nextStepFile: '{workflow_path}/steps-a/step-03-map-architecture.md'
workflowFile: '{workflow_path}/workflow.md'
activityWorkflowFile: '{workflow_path}/workflow-analysis.md'
---

# Step 2: Scan Codebase

## STEP GOAL:

Build a mental model of the codebase through systematic exploration of structure, tech stack, and entry points.

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

- 🎯 Focus only on scanning structure, tech stack, entry points, configuration, and build pipeline
- 🚫 FORBIDDEN to begin deep architectural analysis — that is the next step
- 💬 Approach: Systematically explore top-level structure and record observations with user
- 📋 Document observations as you go — structure, stack, patterns

## EXECUTION PROTOCOLS:

- 🎯 Map directory structure, identify tech stack, locate entry points
- 💾 Document structure overview, tech stack, entry points, configuration, pipeline, and initial patterns
- 📖 Use the question and scope defined in Step 1 to guide scanning focus
- 🚫 Do not trace data flows or map dependencies in detail yet

## CONTEXT BOUNDARIES:

- Available context: Analysis question, scope, output format, and time box from Step 1
- Focus: High-level codebase reconnaissance
- Limits: No deep architectural mapping — stay at survey level
- Dependencies: Step 1 must be complete (question and scope defined)

## Sequence of Instructions (Do not deviate, skip, or optimize)

### 1. Read Project Structure

Start with a directory listing of the root and first two levels:

- Note the top-level folders and what they suggest (e.g., `src/`, `lib/`, `tests/`, `docs/`)
- Identify organizational patterns: by feature, by layer, by module, flat
- Note any unusual or project-specific folders

Record observations:

```
Root structure:
- src/ — Application source code
- tests/ — Test suites
- scripts/ — Build and utility scripts
- docs/ — Documentation
- ...
```

### 2. Identify Tech Stack and Frameworks

Read key configuration files:

| File | Reveals |
|------|---------|
| `package.json` / `requirements.txt` / `Cargo.toml` | Dependencies, scripts, project metadata |
| `tsconfig.json` / `pyproject.toml` | Language configuration |
| `.env.example` / `.env.template` | Environment variables needed |
| `docker-compose.yml` / `Dockerfile` | Container setup, services |
| `Makefile` / `justfile` | Build commands |

Document the stack:

```
Tech stack:
- Language: TypeScript 5.x
- Framework: Next.js 14
- Database: PostgreSQL via Prisma
- Testing: Vitest + Playwright
- Deployment: Docker → AWS ECS
```

### 3. Map Entry Points

Find where execution starts:

- **Web app:** Main page/route, layout files, app entry
- **API:** Server entry, route definitions, middleware chain
- **CLI:** Main command file, argument parsing
- **Library:** Exported modules, public API surface

### 4. Read Configuration Files

Scan for configuration that shapes behavior:

- Environment configuration (dev/staging/prod differences)
- Feature flags or toggles
- Routing configuration
- Database connection setup
- Third-party service configuration (auth, payments, email)

### 5. Identify Build and Deploy Pipeline

Look for:

- CI/CD configuration (`.github/workflows/`, `.gitlab-ci.yml`, `Jenkinsfile`)
- Build scripts and what they produce
- Deployment targets and process
- Environment-specific builds

### 6. Note Patterns Observed

As you scan, note initial observations about:

- Code organization style (monolith, monorepo, microservices)
- Naming conventions (files, folders, variables)
- Test organization (co-located, separate folder, both)
- Documentation level (thorough, sparse, outdated)
- Apparent code quality signals (linting config, formatting config, type strictness)

### 7. Verify Checklist

- [ ] Directory structure mapped (top 2 levels)
- [ ] Tech stack and versions identified
- [ ] Entry points located
- [ ] Configuration files read
- [ ] Build/deploy pipeline identified
- [ ] Initial patterns and conventions noted

### 8. Present MENU OPTIONS

Display: "**Select an Option:** [C] Continue to Step 3: Map Architecture"

#### Menu Handling Logic:
- IF C: Update agent dialog, then load, read entire file, then execute {nextStepFile}
- IF Any other comments or queries: help user respond then [Redisplay Menu Options]

#### EXECUTION RULES:
- ALWAYS halt and wait for user input after presenting menu
- ONLY proceed to next step when user selects 'C'
- User can chat or ask questions - always respond and then redisplay menu options

## CRITICAL STEP COMPLETION NOTE

ONLY WHEN the codebase scan is complete and observations documented will you then load and read fully `{nextStepFile}` to execute.

---

## 🚨 SYSTEM SUCCESS/FAILURE METRICS

### ✅ SUCCESS:
- Directory structure mapped (top 2 levels)
- Tech stack and versions identified
- Entry points located
- Configuration files read
- Build/deploy pipeline identified
- Initial patterns and conventions noted

### ❌ SYSTEM FAILURE:
- Jumping into deep architecture analysis before completing the scan
- Skipping configuration or build pipeline investigation
- Not documenting observations systematically

**Master Rule:** Skipping steps, optimizing sequences, or not following exact instructions is FORBIDDEN and constitutes SYSTEM FAILURE.
