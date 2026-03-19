# Stage 03: Backend Implementation

## Inputs
| Source | File/Location | Section/Scope | Why |
|--------|--------------|---------------|-----|
| Previous stage | `../02-backend-schema-design/output/payload-customizations.md` | Full file | Details schema changes to implement |
| Previous stage | `../02-backend-schema-design/output/access-control-plan.md` | Full file | Access control rules to implement |
| Previous stage (optional) | `../02-backend-schema-design/output/schema-extensions.ts` | Full file | Custom fields to implement |
| Reference | `../../references/conventions-reference.md` | "Pattern 15: Shared Constants" | For defining shared constants in code |
| Reference | `../../examples/payloadcms-implementation-example.md` | Full file | Example backend implementation |

## Process
### Placeholders Used
- {{DATABASE_TYPE}}: Database type selected during setup
- {{DEPLOYMENT_TARGET}}: Deployment target selected during setup
1. Clone or initialize the template repo (pnpx create-payload-app my-site -t website)
2. Apply schema customizations to payload.config.ts (modify collections, add custom fields, configure globals)
3. Implement any required custom hooks or access control functions
4. Test admin panel locally to verify content creation/editing works
5. Validate authentication and access control
6. Test draft/live preview functionality

## Outputs
| Artifact | Location | Format |
|----------|----------|--------|
| Backend setup documentation | `output/backend-setup.md` | Setup instructions and validation steps |
| Customized Payload CMS backend | `src/` (in generated workspace) | Functional backend code |
