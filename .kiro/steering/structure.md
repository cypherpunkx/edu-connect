# Project Structure

## Root Level Organization

```
educonnect-platform/
├── backend/                 # Express.js API server
├── frontend/               # Next.js application  
├── .kiro/                  # Kiro AI assistant configuration
├── .husky/                 # Git hooks configuration
├── docker-compose.yml      # Production Docker setup
├── docker-compose.dev.yml  # Development Docker setup
└── package.json           # Root workspace configuration
```

## Backend Structure (`/backend`)

```
backend/
├── src/
│   ├── config/         # Configuration files (database, auth, etc.)
│   ├── controllers/    # Route controllers (HTTP request handlers)
│   ├── services/       # Business logic layer
│   ├── repositories/   # Data access layer (database operations)
│   ├── models/         # Database models and schemas
│   ├── middleware/     # Express middleware (auth, validation, etc.)
│   ├── utils/          # Utility functions and helpers
│   └── types/          # TypeScript type definitions
├── Dockerfile          # Production container
├── Dockerfile.dev      # Development container
└── package.json        # Backend dependencies and scripts
```

## Frontend Structure (`/frontend`)

```
frontend/
├── src/
│   ├── components/     # React components (organized by feature/type)
│   ├── pages/          # Next.js pages (file-based routing)
│   ├── hooks/          # Custom React hooks
│   ├── utils/          # Utility functions and helpers
│   ├── types/          # TypeScript type definitions
│   ├── lib/            # Library configurations (TanStack Query, etc.)
│   └── styles/         # CSS styles and Tailwind configurations
├── public/             # Static assets
├── Dockerfile          # Production container
├── Dockerfile.dev      # Development container
└── package.json        # Frontend dependencies and scripts
```

## Code Organization Patterns

### Backend Patterns

- **Controllers**: Handle HTTP requests, delegate to services
- **Services**: Contain business logic, orchestrate repositories
- **Repositories**: Direct database operations using Drizzle ORM
- **Models**: Database schema definitions and validation
- **Middleware**: Reusable request processing (auth, logging, validation)

### Frontend Patterns

- **Components**: Organized by feature or UI type (forms, layouts, etc.)
- **Pages**: Next.js file-based routing structure
- **Hooks**: Custom React hooks for state management and side effects
- **Utils**: Pure functions for data transformation and helpers

## Path Aliases

### Backend TypeScript Paths

- `@/*` → `./src/*`
- `@/config/*` → `./src/config/*`
- `@/controllers/*` → `./src/controllers/*`
- `@/services/*` → `./src/services/*`
- `@/repositories/*` → `./src/repositories/*`
- `@/models/*` → `./src/models/*`
- `@/middleware/*` → `./src/middleware/*`
- `@/utils/*` → `./src/utils/*`
- `@/types/*` → `./src/types/*`

### Frontend TypeScript Paths

- `@/*` → `./src/*`
- `@/components/*` → `./src/components/*`
- `@/pages/*` → `./src/pages/*`
- `@/hooks/*` → `./src/hooks/*`
- `@/utils/*` → `./src/utils/*`
- `@/types/*` → `./src/types/*`
- `@/lib/*` → `./src/lib/*`
- `@/styles/*` → `./src/styles/*`

## File Naming Conventions

- **Components**: PascalCase (e.g., `UserProfile.tsx`)
- **Pages**: kebab-case (e.g., `user-profile.tsx`)
- **Utilities**: camelCase (e.g., `formatDate.ts`)
- **Types**: PascalCase with `.types.ts` suffix
- **Constants**: UPPER_SNAKE_CASE in `constants.ts` files

## Import Organization

1. External libraries (React, Next.js, etc.)
2. Internal modules using path aliases
3. Relative imports
4. Type-only imports at the end
