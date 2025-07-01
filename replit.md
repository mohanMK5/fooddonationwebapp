# Food Bridge - Food Donation Platform

## Overview

Food Bridge is a full-stack web application designed to connect food donors with NGOs to reduce waste and help communities in need. The platform enables donors (restaurants, stores, individuals) to post available food donations, while NGOs can browse and accept these donations to distribute to those in need.

## System Architecture

### Frontend Architecture
- **Framework**: React with TypeScript using Vite as the build tool
- **Routing**: Wouter for client-side routing
- **State Management**: TanStack Query for server state management and local storage for authentication
- **UI Components**: Shadcn/ui component library built on Radix UI primitives
- **Styling**: Tailwind CSS with CSS variables for theming
- **Forms**: React Hook Form with Zod validation

### Backend Architecture
- **Runtime**: Node.js with Express.js framework
- **Language**: TypeScript with ES modules
- **Database**: PostgreSQL with Drizzle ORM
- **Database Provider**: Neon Database (serverless PostgreSQL)
- **Session Management**: PostgreSQL-based sessions using connect-pg-simple
- **Development**: In-memory storage fallback for development

### Project Structure
- `client/`: Frontend React application
- `server/`: Backend Express server
- `shared/`: Shared TypeScript schemas and types
- `migrations/`: Database migration files

## Key Components

### Authentication System
- Role-based authentication (Donor vs NGO)
- Local storage-based session management
- Protected routes with role verification
- Mock authentication for development (to be replaced with real auth)

### Database Schema
- **Users Table**: Stores user information with role differentiation
- **Donations Table**: Manages food donation listings with status tracking
- **Schema Validation**: Drizzle-Zod integration for type-safe database operations

### User Interfaces
- **Home Page**: Landing page with hero section and feature overview
- **Authentication**: Combined login/register form with role selection
- **Donor Dashboard**: Interface for creating and managing food donations
- **NGO Dashboard**: Interface for browsing and accepting available donations
- **Navigation**: Responsive navbar with role-based menu items

### Data Models
- **User**: Contains id, name, email, password, role, and timestamps
- **Donation**: Contains food details, quantity, expiry, location, contact info, status, and relationships

## Data Flow

1. **User Registration/Login**: Users select their role (donor/NGO) and authenticate
2. **Donation Creation**: Donors create listings with food details, quantity, and pickup information
3. **Donation Discovery**: NGOs browse available donations with filtering capabilities
4. **Donation Acceptance**: NGOs can accept donations, changing status from 'pending' to 'accepted'
5. **Status Management**: Real-time updates on donation status across the platform

## External Dependencies

### Frontend Dependencies
- **UI Framework**: React, React DOM, React Router (Wouter)
- **State Management**: TanStack React Query
- **UI Components**: Radix UI primitives, Shadcn/ui
- **Forms**: React Hook Form, Hookform Resolvers
- **Styling**: Tailwind CSS, Class Variance Authority, clsx
- **Icons**: Lucide React
- **Date Handling**: date-fns
- **Carousel**: Embla Carousel React

### Backend Dependencies
- **Server**: Express.js with TypeScript support
- **Database**: Drizzle ORM with PostgreSQL dialect
- **Database Provider**: Neon Database serverless
- **Session Store**: connect-pg-simple for PostgreSQL sessions
- **Validation**: Zod for schema validation
- **Development**: tsx for TypeScript execution

### Development Tools
- **Build Tool**: Vite with React plugin
- **TypeScript**: Full TypeScript support with strict mode
- **Database Tools**: Drizzle Kit for migrations and schema management
- **Development**: Replit-specific plugins for error handling

## Deployment Strategy

### Development Environment
- **Local Development**: `npm run dev` starts both frontend and backend
- **Database**: Drizzle push commands for schema updates
- **Hot Reload**: Vite HMR for frontend, tsx for backend auto-restart

### Production Build
- **Frontend**: Vite builds static assets to `dist/public`
- **Backend**: esbuild bundles server code to `dist/index.js`
- **Database**: Environment variable-based PostgreSQL connection
- **Startup**: Single `npm start` command runs the production server

### Environment Configuration
- **DATABASE_URL**: PostgreSQL connection string (required)
- **NODE_ENV**: Environment mode (development/production)
- **Static Assets**: Express serves built frontend from production build

### Scaling Considerations
- Serverless-ready architecture with Neon Database
- Stateless server design with external session storage
- CDN-ready static asset serving
- Environment-based configuration for multiple deployments

## Changelog

```
Changelog:
- July 01, 2025. Initial setup
```

## User Preferences

```
Preferred communication style: Simple, everyday language.
```