# Stage 05: Frontend Implementation & Deployment

## Inputs
| Source | File/Location | Section/Scope | Why |
|--------|--------------|---------------|-----|
| Previous stage | `../04-frontend-planning/output/frontend-specs.md` | Full file | Frontend component and styling specifications |
| Previous stage | `../03-backend-implementation/output/` | Backend API confirmation | Verified backend functionality |
| Reference | `../../references/conventions-reference.md` | "Pattern 9: Bundled Skills" | For incorporating vercel-react-best-practices skill |
| Reference | `../../references/conventions-reference.md` | "Pattern 15: Shared Constants" | For defining shared constants in frontend code |

## Process
### Placeholders Used
- {{DATABASE_TYPE}}: Database type selected during setup
- {{DEPLOYMENT_TARGET}}: Deployment target selected during setup
1. Frontend work:
    - Modify Tailwind config for brand colors
    - Customize layout blocks in components/ if needed
    - Update page templates in src/app/ to match design
    - Implement custom components for specific content types
    - Ensure SEO plugin integration works
    - Test search functionality
    - Verify redirects work
    - Test dark mode toggle
2. Deployment steps:
    - Choose deployment target
    - Set up environment variables (DATABASE_URL, PAYLOAD_SECRET, etc.)
    - Configure hosting-specific services (Databases, Storage, etc.)
    - Run pnpm build to verify production build
    - Test deployment preview/staging
    - Set up custom domain if needed
    - Configure webhooks for on-demand revalidation if applicable
    - Implement monitoring and logging

## Outputs
| Artifact | Location | Format |
|----------|----------|--------|
| Deployed website | Production URL | Live website |
| Deployment summary | `output/deployment-summary.md` | Env vars, build process, hosting configuration, and any post-deployment validation steps |
