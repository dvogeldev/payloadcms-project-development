# PayloadCMS Project Development Setup

<!-- Agent instructions: Read this file when the user types "setup". Ask ALL questions
     in a single conversational pass. The user should be able to answer everything in one
     message. Collect answers. Replace placeholders across the specified files. After all
     replacements, verify no {{PLACEHOLDER}} patterns remain in the workspace. -->

<!-- Questionnaire design rules:
     1. FLAT STRUCTURE: No category groupings. Just a numbered list of questions.
     2. ALL AT ONCE: Every question appears in one pass. The user answers in one message.
     3. SYSTEM-LEVEL ONLY: Questions configure the production system, not a specific run.
        Per-run details (project name, topic, audience) are collected conversationally
        at the start of each pipeline run by the entry stage.
     4. DERIVE, DON'T ASK: If a field can be derived from other answers, the agent fills
         it in without asking. List derived fields under the question they depend on.
     5. SENSIBLE DEFAULTS: Every question should have a default or example so the user
         can skip what they don't care about.
     6. ASK ONCE, NEVER AGAIN: After setup, the user should never be asked these questions
         again. The answers are baked into the workspace files permanently.
     7. EXAMPLES OVER DESCRIPTIONS: For voice/style questions, ask for concrete examples
         (sentences that sound right, sentences that sound wrong, specific error patterns)
         rather than abstract descriptions. Examples are pattern-matchable. Descriptions
         require interpretation and produce weaker constraints. -->

### Q1: What is the name of your PayloadCMS project?
- Placeholder: `{{PROJECT_NAME}}`
- Files: `CLAUDE.md`, `CONTEXT.md`
- Type: free text
- Default: my-payloadcms-site

### Q2: What type of website are you building?
- Placeholder: `{{WEBSITE_TYPE}}`
- Files: `stages/01-discovery/CONTEXT.md`
- Type: selection
- Options: Blog, Business site, Portfolio, E-commerce, Documentation, Other

### Q3: Do you want to include MVP development as an optional precursor stage?
- Type: yes/no
- Default: yes
- If NO: Remove `stages/00-mvp-builder/` entirely
- If YES: Keep it

### Q4: Which deployment target do you plan to use?
- Placeholder: `{{DEPLOYMENT_TARGET}}`
- Files: `stages/05-frontend-implementation-deployment/CONTEXT.md`
- Type: selection
- Options: DigitalOcean, Vercel, Cloudflare, AWS, Other

### Q5: What database will you use with PayloadCMS?
- Placeholder: `{{DATABASE_TYPE}}`
- Files: `stages/03-backend-implementation/CONTEXT.md`, `stages/05-frontend-implementation-deployment/CONTEXT.md`
- Type: selection
- Options: PostgreSQL, MongoDB, SQLite, MySQL

### Q6: Do you want to bundle the vercel-react-best-practices skill for frontend optimization?
- Type: yes/no
- Default: yes
- If NO: Don't bundle the skill
- If YES: Bundle the vercel-react-best-practices skill

### Q7: Do you want to include SEO configuration in your PayloadCMS setup?
- Type: yes/no
- Default: yes
- If NO: Remove SEO references from stages
- If YES: Keep SEO configuration

### Q8: Do you want to include search functionality in your PayloadCMS setup?
- Type: yes/no
- Default: yes
- If NO: Remove search references from stages
- If YES: Keep search functionality

### Q9: What is your preferred CSS framework/styling approach?
- Placeholder: `{{STYLING_APPROACH}}`
- Files: `stages/04-frontend-planning/CONTEXT.md`, `stages/05-frontend-implementation-deployment/CONTEXT.md`
- Type: selection
- Options: Tailwind CSS, CSS Modules, Styled Components, Plain CSS, Other

### Q10: Do you need multi-language/i18n support?
- Placeholder: `{{NEEDS_I18N}}`
- Files: `stages/02-mapping/CONTEXT.md`, `stages/04-frontend-planning/CONTEXT.md`
- Type: yes/no
- Default: no
- If NO: No i18n configuration
- If YES: Include i18n setup guides

---
After all replacements, scan the entire workspace for remaining `{{` patterns. If any remain, ask for the missing info.

## After Onboarding

Your PayloadCMS project development workspace has been configured with:
- Project name: {{PROJECT_NAME}}
- Website type: {{WEBSITE_TYPE}}
- Deployment target: {{DEPLOYMENT_TARGET}}
- Database: {{DATABASE_TYPE}}
- Styling approach: {{STYLING_APPROACH}}
- MVP stage: {{#IF_INCLUDE_MVP}}included{{/IF_INCLUDE_MVP}}
- Vercel best practices skill: {{#IF_VERCEL_SKILL}}bundled{{/IF_VERCEL_SKILL}}
- SEO: {{#IF_INCLUDE_SEO}}included{{/IF_INCLUDE_SEO}}
- Search: {{#IF_INCLUDE_SEARCH}}included{{/IF_INCLUDE_SEARCH}}
- i18n support: {{#IF_NEEDS_I18N}}included{{/IF_NEEDS_I18N}}

To begin building your PayloadCMS website, navigate to this workspace and run the pipeline stages in order starting with Stage 01: Discovery.