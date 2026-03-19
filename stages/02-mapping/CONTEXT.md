# Stage 02: Backend Schema Design

## Inputs
| Source | File/Location | Section/Scope | Why |
|--------|--------------|---------------|-----|
| Previous stage | `../01-discovery/output/requirements.md` | Full file | Lists required content types, fields, user roles, features |
| Reference | `../../references/conventions-reference.md` | "Pattern 10: Specs Are Contracts" | Understand that specs define WHAT and WHEN, not HOW |
| Reference | `../../references/examples/payloadcms-backend-example.md` | Full file | Example of PayloadCMS schema design |

## Process
1. Review template's existing collections (Users, Posts, Pages, Media, Categories) and globals (Header, Footer)
2. Determine which to keep/modify/remove
3. Design any custom fields or relationships needed for specific content
4. Configure access control rules per role
5. Plan SEO/search configuration
6. Decide on layout builder usage for Posts/Pages
7. Note any custom endpoints/hooks required

## Outputs
| Artifact | Location | Format |
|----------|----------|--------|
| Payload customizations document | `output/payload-customizations.md` | Details changes to template schema |
| Access control plan | `output/access-control-plan.md` | Specifies role-based permissions |
| Schema extensions (optional) | `output/schema-extensions.ts` | TypeScript file for custom fields |
