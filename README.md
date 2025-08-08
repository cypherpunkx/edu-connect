# EduConnect Platform

A comprehensive global educational platform that combines forum discussions, free and paid courses, educational events, education news, and real-time chat in a modern, scalable, and collaborative web application.

## Features

- 🎓 **Course Management**: Free and paid courses with multimedia content
- 💬 **Forum Discussions**: Public and private forums with real-time updates
- 📅 **Event Management**: Educational events with registration and payments
- 💬 **Real-time Chat**: Personal and group messaging
- 📰 **News & Content**: Educational news and articles
- 👨‍💼 **Admin Dashboard**: Comprehensive content and user management
- 💳 **Payment Integration**: Secure payment processing for courses and events
- 🔐 **Authentication**: Email and Google OAuth login

## Tech Stack

### Backend

- **Runtime**: Node.js with TypeScript
- **Framework**: Express.js
- **Database**: MySQL with Drizzle ORM
- **Real-time**: Socket.IO
- **Authentication**: JWT + Google OAuth
- **Validation**: Valibot
- **File Upload**: Multer

### Frontend

- **Framework**: Next.js 14 with TypeScript
- **Styling**: TailwindCSS + shadcn/ui
- **State Management**: TanStack Query
- **Real-time**: Socket.IO Client
- **Animations**: Framer Motion

### DevOps

- **Package Manager**: pnpm
- **Containerization**: Docker & Docker Compose
- **Code Quality**: ESLint, Prettier, Husky
- **Testing**: Vitest

## Getting Started

### Prerequisites

- Node.js 18+
- pnpm 8+
- Docker & Docker Compose (optional)

### Installation

1. **Clone the repository**

   ```bash
   git clone <repository-url>
   cd educonnect-platform
   ```

2. **Install dependencies**

   ```bash
   pnpm install
   ```

3. **Set up environment variables**

   ```bash
   cp .env.example .env
   # Edit .env with your configuration
   ```

4. **Start development with Docker (Recommended)**

   ```bash
   pnpm docker:dev
   ```

   Or start manually:

   ```bash
   # Start database services
   docker-compose -f docker-compose.dev.yml up mysql redis -d
   
   # Start development servers
   pnpm dev
   ```

### Available Scripts

- `pnpm dev` - Start development servers
- `pnpm build` - Build for production
- `pnpm start` - Start production servers
- `pnpm lint` - Run linting
- `pnpm lint:fix` - Fix linting issues
- `pnpm format` - Format code with Prettier
- `pnpm test` - Run tests
- `pnpm docker:dev` - Start development environment with Docker
- `pnpm docker:prod` - Start production environment with Docker

## Project Structure

```
educonnect-platform/
├── backend/                 # Express.js API server
│   ├── src/
│   │   ├── config/         # Configuration files
│   │   ├── controllers/    # Route controllers
│   │   ├── services/       # Business logic
│   │   ├── repositories/   # Data access layer
│   │   ├── models/         # Database models
│   │   ├── middleware/     # Express middleware
│   │   ├── utils/          # Utility functions
│   │   └── types/          # TypeScript types
│   ├── Dockerfile
│   └── package.json
├── frontend/               # Next.js application
│   ├── src/
│   │   ├── components/     # React components
│   │   ├── pages/          # Next.js pages
│   │   ├── hooks/          # Custom React hooks
│   │   ├── utils/          # Utility functions
│   │   ├── types/          # TypeScript types
│   │   ├── lib/            # Library configurations
│   │   └── styles/         # CSS styles
│   ├── Dockerfile
│   └── package.json
├── docker-compose.yml      # Production Docker setup
├── docker-compose.dev.yml  # Development Docker setup
└── package.json           # Root package.json
```

## Development Workflow

1. **Code Quality**: Pre-commit hooks ensure code formatting and linting
2. **Conventional Commits**: Commit messages follow conventional format
3. **Testing**: Write tests for new features and bug fixes
4. **Documentation**: Update documentation for API changes

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'feat: add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
