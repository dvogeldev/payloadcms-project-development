# PayloadCMS Project Development Workspace

This workspace provides a structured approach to building PayloadCMS websites through a guided six-stage process. It follows the Interpted Context Methodology (a specialized framework for systematic project development) to ensure consistency, quality, and completeness in PayloadCMS project delivery.

## Overview

The PayloadCMS Project Development Workspace is designed to help teams build robust, scalable websites using PayloadCMS - a powerful, open-source headless CMS built on Node.js with React/Admin interface. Rather than starting from scratch each time, this workspace provides a repeatable process that captures domain knowledge, establishes clear stage contracts, and generates production-ready codebases.

## The Six-Stage Development Process

### Stage 0: MVP Development (Optional Precursor)

**Purpose**: Rapidly validate core concepts before full investment

- Optional stage for quickly building a minimum viable product
- Can use online builders, LLMs, or rapid prototyping tools
- Helps validate assumptions and gather early feedback
- Output feeds into Stage 1 as insights and refined requirements

### Stage 1: Discovery

**Purpose**: Understand the problem domain and user needs

- Conversational exploration of stakeholder goals, target audience, and workflows
- Analysis of competitor sites and content examples (if migrating)
- Identification of distinct stages, handoff points, and natural breakpoints
- Documentation of shared context (brand voice, design system) and user-specific details
- Discovery of relevant skills, tool prerequisites, and optional stages
- **Output**: Workflow map detailing stages, inputs/outputs, context, variables, and selected skills

### Stage 2: Backend Schema Design

**Purpose**: Define what content will be managed and how it's structured

- Review of existing PayloadCMS collections (Users, Posts, Pages, Media, Categories)
- Determination of which collections to keep, modify, or remove
- Design of custom fields and relationships for specific content types
- Planning of access control rules per user role
- Decision on layout builder usage for dynamic page building
- Planning of SEO/search configuration and custom endpoints/hooks
- **Output**:
  - Payload customizations document (schema changes)
  - Access control plan (role-based permissions)
  - Schema extensions (custom field definitions, if needed)

### Stage 3: Backend Implementation

**Purpose**: Build the functional content management system

- Initialization of PayloadCMS project using website template
- Application of schema customizations to payload.config.ts
- Implementation of custom hooks and access control functions
- Configuration of database connection (MongoDB in this implementation)
- Testing of admin panel for content creation/editing workflows
- Validation of authentication, access control, and draft/live preview functionality
- **Output**:
  - Backend setup documentation with validation steps
  - Functional Payload CMS backend code in src/ directory

### Stage 4: Frontend Planning

**Purpose**: Design the user experience and interface

- Mapping of template frontend components to design requirements
- Planning of custom layout blocks needed for the page builder
- Determination of data fetching strategy for pages and posts
- Planning of header/footer content from PayloadCMS globals
- Outlining of routing structure (static pages vs dynamic routes)
- Planning of SEO meta tag implementation and search UI integration
- Planning of redirect handling if needed
- **Output**: Frontend specifications document detailing component map, layout block requirements, routing plan, and styling approach

### Stage 5: Frontend Implementation & Deployment

**Purpose**: Build and launch the public-facing website

- Frontend development:
  - Modification of Tailwind config for brand colors
  - Customization and creation of layout blocks/components
  - Implementation of page templates matching the design
  - Ensuring SEO plugin integration works correctly
  - Testing search functionality and verifying redirects
  - Implementing dark mode toggle and other UI features
- Deployment steps:
  - Configuration of hosting environment (DigitalOcean in this implementation)
  - Setup of environment variables (DATABASE_URL, PAYLOAD_SECRET, etc.)
  - Configuration of hosting-specific services (databases, storage)
  - Execution of production build to verify functionality
  - Testing of deployment preview/staging environment
  - Setup of custom domain (if applicable)
  - Configuration of webhooks for on-demand revalidation
  - Implementation of monitoring and logging solutions
- **Output**:
  - Deployed website at production URL
  - Deployment summary documenting environment variables, build process, hosting configuration, and validation steps

## Key Benefits of This Approach

1. **Consistency**: Repeatable process ensures quality across projects
2. **Clarity**: Explicit stage contracts prevent misunderstandings
3. **Efficiency**: Reusable components and patterns reduce development time
4. **Quality**: Built-in validation checkpoints catch issues early
5. **Knowledge Retention**: Process captures organizational learning
6. **Scalability**: Approach works for both simple sites and complex applications

## Getting Started

To use this workspace for your own PayloadCMS project:

1. Run the `setup` command to configure your project-specific details:
   - Project name
   - Website type (blog, business site, portfolio, etc.)
   - Deployment target (DigitalOcean, Vercel, AWS, etc.)
   - Database choice (PostgreSQL, MongoDB, SQLite, MySQL)
   - Styling approach (Tailwind CSS, CSS Modules, etc.)
   - Optional features (MVP stage, SEO, search, i18n, Vercel best practices)

2. Progress through the stages in order:
   - Complete Stage 1: Discovery to map your workflow
   - Complete Stage 2: Backend Schema Design to define your content structure
   - Complete Stage 3: Backend Implementation to build your CMS
   - Complete Stage 4: Frontend Planning to design your user interface
   - Complete Stage 5: Frontend Implementation & Deployment to build and launch your site

3. Each stage produces tangible outputs that feed into the next stage, ensuring continuity and reducing rework.

## Files in This Workspace

- `status` - Shows current progress through the development pipeline
- `CLAUDE.md` - Agent guidelines and workspace-specific instructions
- `CONTEXT.md` - Workspace overview and task routing information
- `setup/` - Contains the onboarding questionnaire for project configuration
- `stages/` - Contains the six stage folders with their respective CONTEXT.md files
- `references/` - Common conventions and example references used across stages

This workspace eliminates guesswork in PayloadCMS project development by providing a clear, structured path from concept to production deployment.
