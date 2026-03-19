# Agent Guidelines for PayloadCMS Project Development Workspace

This file extends the universal VIBE-CODE-RULES.md guidelines with project-specific context for the PayloadCMS project development workspace.

## Extending VIBE-CODE-RULES.md

All principles from VIBE-CODE-RULES.md apply unless explicitly overridden below:

### Workspace-Specific Context
- **Tech Stack**: PayloadCMS, Node.js, React/Next.js, Tailwind CSS
- **Deployment Targets**: DigitalOcean, Vercel, Cloudflare (configurable via setup)
- **Database Options**: PostgreSQL, MongoDB, SQLite, MySQL (configurable via setup)
- **API**: REST (PayloadCMS admin API) and GraphQL (via plugins)
- **Styling**: Tailwind CSS (primary), with options for CSS Modules, Styled Components, or Plain CSS

### File Organization Specifics
- Generated workspaces follow MWP conventions with staged outputs
- Backend code lives in `src/` directory after Stage 3
- Frontend code lives in `src/app/` (Next.js App Router) after Stage 5
- Configuration files: `payload.config.ts`, `.env.example`

### PayloadCMS-Specific Rules
- **Schema Modifications**: All PayloadCMS schema changes must be documented in `payload-customizations.md`
- **Access Control**: Role-based permissions must be defined in `access-control-plan.md`
- **Environment Variables**: Must be documented in `deployment-summary.md` with `.env.example` template
- **Custom Hooks**: Any PayloadCMS hooks must be TypeScript files with proper typing
- **Frontend Components**: Must follow Next.js App Router conventions and PayloadCMS data fetching patterns

### Quality Guidelines Specific to This Workspace
- **PayloadCMS Version**: Use latest stable version unless otherwise specified
- **Node.js Version**: Use LTS version (currently 18.x or 20.x)
- **Testing**: Write integration tests using PayloadCMS testing utilities
- **Type Safety**: All custom TypeScript must be strictly typed (no `any`)
- **Performance**: Follow Vercel and PayloadCMS performance best practices
- **Security**: Implement proper PayloadCMS access control and validate all inputs