# Step 5: SEO Keywords

## Purpose

Capture target keywords for each language to guide content creation.

## Context for Agent

SEO keywords inform both content strategy and technical implementation. Keywords should align with user search intent and business goals.

## Instructions

1. **Gather existing keyword research**

   Ask: "Do you have keywords you want to rank for?"

   If yes:
   - Document provided keywords
   - Organize by category/intent

   If no:
   - Help brainstorm based on services and location

2. **Keyword categories**

   Organize keywords by intent:

   | Category | Intent | Example |
   |----------|--------|---------|
   | **Service** | Looking for specific service | "bilservice Öland" |
   | **Location** | Near me searches | "bilverkstad norra Öland" |
   | **Problem** | Has a specific issue | "AC reparation bil" |
   | **Brand** | Looking for business | "Källa Fordonservice" |

3. **Translate/adapt keywords for each language**

   Keywords don't translate directly. For each language:
   - What would a native speaker search?
   - Local terminology variations
   - Common misspellings to consider

4. **Keyword usage guidelines**

   Document how keywords should be used:
   - Page titles and meta descriptions
   - Headings (H1, H2)
   - Body content (natural, not stuffed)
   - Image alt text
   - URL slugs

5. **Document in output**
   - Fill in SEO Keywords section by language
   - Add keyword usage guidelines

## Example for Mechanic

```
Swedish:
- Bilverkstad Öland
- Bilservice norra Öland
- AC service bil
- Däckbyte Löttorp
- Husbilservice Öland

English:
- Car repair Öland
- Mechanic northern Öland
- Motorhome service Sweden
- Auto repair near Byxelkrok

German:
- Autowerkstatt Öland
- KFZ-Service Schweden
- Wohnmobil Reparatur Öland
```

## Agent Dialog Update

After completing this step, update the agent dialog:

```markdown
### Step 5: SEO Keywords
**Q:** Target keywords for each language? Existing research?
**A:** [Keywords captured by language and category]
**Documented in:** content-language.md (SEO Keywords section)
**Key insights:** [Keyword strategy, usage guidelines]
**Status:** Complete
**Timestamp:** [HH:MM]
```

## Next Step

<action>After completing this step, load and execute: `step-05.5-content-structure.md`</action>

## State Update

Update frontmatter of output file:

```yaml
stepsCompleted: ['step-01-init.md', 'step-02-personality.md', 'step-03-tone.md', 'step-04-languages.md', 'step-05-seo-keywords.md']
keywords_captured: true
```
