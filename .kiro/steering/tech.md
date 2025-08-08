---
inclusion: always
---

# Technology Stack & Development Guidelines

## Architecture Requirements

- **Monorepo**: pnpm workspaces - always use `pnpm --filter <package>` for package-specific commands
- **Package Manager**: pnpm (>=8.0.0) - never use npm or yarn
- **Node.js**: >=18.0.0 required for both backend and frontend
- **TypeScript**: Strict mode enabled - all code must be fully typed

## Backend Technology Stack

- **Runtime**: Node.js with TypeScript (strict mode)
- **Framework**: Express.js with async/await patterns
- **Database**: MySQL with Drizzle ORM - use schema-first approach
- **Real-time**: Socket.IO for live features
- **Authentication**: JWT tokens + Google OAuth integration
- **Validation**: Valibot schemas (shared with frontend)
- **File Upload**: Multer middleware with type validation
- **Email**: Nodemailer for transactional emails

### Backend Code Conventions

- Use path aliases: `@/` for src root, `@/controllers/*`, `@/services/*`, etc.
- Controllers handle HTTP only - delegate business logic to services
- Services contain business logic - orchestrate repositories
- Repositories handle database operations using Drizzle ORM
- Always use async/await, never callbacks or raw promises
- Validate all inputs using Valibot schemas
- Use proper HTTP status codes and error handling

## Frontend Technology Stack

- **Framework**: Next.js 15.4.6 with App Router (not Pages Router)
- **Styling**: TailwindCSS + shadcn/ui components only
- **State Management**: TanStack Query for server state, React state for UI
- **Real-time**: Socket.IO Client for live updates
- **Animations**: Framer Motion for complex animations
- **Icons**: Lucide React icons exclusively
- **Validation**: Valibot schemas (shared with backend)

### Frontend Code Conventions

- Use App Router file conventions: `page.tsx`, `layout.tsx`, `loading.tsx`
- Components in PascalCase, files in kebab-case
- Use shadcn/ui components before creating custom ones
- TanStack Query for all server state management
- Use TypeScript path aliases: `@/components/*`, `@/lib/*`, etc.
- Prefer server components when possible, use 'use client' sparingly

## Development Tools & Quality

- **Linting**: ESLint with strict TypeScript rules
- **Formatting**: Prettier with consistent configuration
- **Git Hooks**: Husky pre-commit hooks for quality checks
- **Testing**: Vitest for unit and integration tests
- **Containerization**: Docker Compose for development and production

## Development Workflow

### Required Commands for Development

```bash
# Preferred development setup
pnpm docker:dev             # Start full environment with Docker

# Manual development (if Docker unavailable)
pnpm dev                    # Start both services
pnpm --filter backend dev   # Backend only (port 3001)
pnpm --filter frontend dev  # Frontend only (port 3000)
```

### Code Quality Requirements

```bash
pnpm lint                   # Must pass before commits
pnpm lint:fix              # Auto-fix linting issues
pnpm format                # Format with Prettier
pnpm test                  # All tests must pass
```

### Database Operations (Backend Only)

```bash
pnpm --filter backend db:generate   # Generate migrations after schema changes
pnpm --filter backend db:migrate    # Apply migrations to database
pnpm --filter backend db:studio     # Open Drizzle Studio for data inspection
```

## Environment & Configuration

- **Environment Files**: Copy `.env.example` to `.env` - required for development
- **Database**: MySQL via Docker Compose (port 3306)
- **Redis**: Via Docker Compose for caching and sessions
- **Ports**: Backend (3001), Frontend (3000), Database (3306)

## Code Style Requirements

### TypeScript Standards

- Strict mode enabled - no `any` types allowed
- Use proper type definitions for all functions and variables
- Prefer interfaces over types for object shapes
- Use enums for constants with multiple values

### Import Organization

1. External libraries (React, Next.js, Express, etc.)
2. Internal modules using path aliases (`@/`)
3. Relative imports (`./`, `../`)
4. Type-only imports last with `import type`

### Error Handling Patterns

- Backend: Use proper HTTP status codes and structured error responses
- Frontend: Use error boundaries and proper error states
- Always handle async operations with try/catch
- Log errors appropriately for debugging

### Database Patterns

- Use Drizzle schema definitions for all tables
- Write migrations for schema changes
- Use repositories for complex queries
- Validate data at both API and database levels
