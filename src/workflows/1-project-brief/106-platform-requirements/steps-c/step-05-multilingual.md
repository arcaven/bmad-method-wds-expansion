# Step 5: Multilingual & SEO

## Purpose

Document language requirements and technical SEO needs.

## Context for Agent

Multilingual setup affects plugin choices, URL structure, and content workflow. SEO requirements inform technical implementation.

## Key Elements

- Language requirements
- URL structure for languages
- Translation workflow
- Technical SEO requirements

## Instructions

1. **Determine language needs**

   Ask: "What languages does the site need to support?"
   - Single language — simpler setup
   - Multiple languages — requires plugin and strategy

2. **If multilingual:**

   **Recommend URL structure:**
   ```
   example.com/           → Primary language (Swedish)
   example.com/en/        → English
   example.com/de/        → German
   ```

   **Plugin recommendation:**
   - **Polylang** — Free tier works, good SEO support
   - **WPML** — More features, paid
   - **TranslatePress** — Visual translation

   **Translation workflow:**
   - Who translates? (client, translator, agency)
   - Full translation or priority pages?
   - Ongoing updates process

   **Technical requirements:**
   - hreflang tags (automatic with good plugins)
   - Language switcher placement
   - Default language handling

3. **SEO technical requirements**

   Document needs:
   - **Meta tags** — Title, description per page
   - **Structured data** — LocalBusiness, Organization
   - **Sitemap** — XML sitemap generation
   - **Robots.txt** — Crawl directives
   - **Page speed** — Core Web Vitals targets
   - **Mobile-first** — Responsive, mobile-optimized

   **SEO plugin recommendation:**
   - **Rank Math** — Feature-rich, free tier excellent
   - **Yoast** — Industry standard, some features paid

4. **Performance targets**

   Discuss realistic targets:
   - Page load time goal (e.g., < 3 seconds on 4G)
   - Core Web Vitals targets
   - Mobile performance priority

5. **Update output document**
   - Fill in Multilingual Requirements section
   - Fill in SEO Requirements section
   - Add Performance Targets


## Agent Dialog Update

After completing this step, update the agent dialog:

```markdown
### [Step Name]
**Q:** [Key questions asked]
**A:** [User responses - summarized]
**Documented in:** platform-requirements.md ([section name])
**Key insights:** [Important decisions or revelations]
**Status:** Complete
**Timestamp:** [HH:MM]
```

## Next Step

After completing multilingual/SEO, proceed to step-06-synthesize.md

## State Update

Update frontmatter of output file:

```yaml
stepsCompleted: ['step-01-init.md', 'step-02-tech-stack.md', 'step-03-integrations.md', 'step-04-contact-strategy.md', 'step-05-multilingual.md']
languages: '[list]'
seo_plugin: '[choice]'
```
