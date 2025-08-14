# Minecraft Premium Account Store

## Overview

This is a full-stack web application for selling premium Minecraft accounts. The project features a gaming-themed frontend with a Minecraft aesthetic, built using React and modern web technologies. The backend provides REST API endpoints for managing account packages, testimonials, contact messages, and orders. The application uses a PostgreSQL database with Drizzle ORM for data persistence and includes a complete e-commerce workflow for purchasing gaming accounts.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
The client-side application is built with React and uses a modern component-based architecture:
- **React Router**: Uses Wouter for lightweight client-side routing
- **State Management**: Zustand for cart state management and React Query for server state
- **UI Framework**: Custom components built on top of Radix UI primitives with shadcn/ui styling
- **Styling**: Tailwind CSS with custom Minecraft-themed color palette and pixel fonts
- **Build Tool**: Vite for fast development and optimized production builds

### Backend Architecture
The server follows a REST API pattern built with Express.js:
- **Framework**: Express.js with TypeScript for type safety
- **Route Organization**: Centralized route registration with modular endpoint definitions
- **Storage Layer**: Abstracted storage interface allowing for different implementations (currently in-memory with database migration planned)
- **Validation**: Zod schemas for request/response validation
- **Error Handling**: Centralized error middleware with proper HTTP status codes

### Data Layer
The application uses a PostgreSQL database with a well-structured schema:
- **ORM**: Drizzle ORM for type-safe database operations and migrations
- **Schema Design**: Four main entities - account packages, testimonials, contact messages, and orders
- **Migrations**: Drizzle Kit handles database schema migrations
- **Type Safety**: Shared TypeScript types between frontend and backend using Drizzle-generated schemas

### Design Patterns
- **Shared Types**: Common schema definitions in `/shared` directory used by both client and server
- **API Client**: Centralized fetch wrapper with error handling and type inference
- **Component Composition**: Reusable UI components with consistent theming
- **Form Management**: React Hook Form with Zod validation for type-safe form handling

### Development Environment
- **Monorepo Structure**: Single repository with client, server, and shared code
- **Hot Reload**: Vite development server with HMR for fast iteration
- **TypeScript**: Full TypeScript coverage across frontend, backend, and shared code
- **Path Aliases**: Configured path mapping for clean imports

## External Dependencies

### Database
- **PostgreSQL**: Primary database using Neon serverless PostgreSQL
- **Connection**: Uses `@neondatabase/serverless` for database connectivity
- **Environment**: Database URL configured via `DATABASE_URL` environment variable

### UI Components
- **Radix UI**: Comprehensive set of accessible, unstyled UI primitives
- **Tailwind CSS**: Utility-first CSS framework for styling
- **Lucide Icons**: Modern icon library for UI elements
- **Font Awesome**: Gaming-specific icons for Minecraft theme

### Development Tools
- **Vite**: Build tool and development server
- **ESBuild**: Fast bundling for production builds
- **PostCSS**: CSS processing with Tailwind and Autoprefixer
- **TypeScript**: Type checking and compilation

### Form and Data Management
- **React Hook Form**: Performant form library with minimal re-renders
- **TanStack Query**: Powerful data synchronization for React
- **Zod**: Schema validation library for type-safe data handling
- **Zustand**: Lightweight state management for client-side state

### Session Management
- **connect-pg-simple**: PostgreSQL session store for Express sessions
- **Express Session**: Server-side session management

### Hosting and Deployment
- **Replit**: Development and hosting platform with integrated tooling
- **Static Assets**: Served via Express static middleware in production