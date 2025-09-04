# Student Feedback Portal

## Overview

A full-stack web application designed for collecting and managing student feedback in educational institutions. The system provides a dual interface: a student-facing form for submitting feedback and an administrative dashboard for reviewing and managing submissions. Built with modern web technologies including React, Express.js, and PostgreSQL, the application emphasizes user experience, data integrity, and responsive design.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
The client-side is built using React 18 with TypeScript, implementing a component-based architecture. The application uses Vite as the build tool for fast development and optimized production builds. Key architectural decisions include:

- **Component Library**: Radix UI components with shadcn/ui styling for consistent, accessible UI elements
- **Styling**: Tailwind CSS with custom design tokens and CSS variables for theming
- **State Management**: TanStack Query (React Query) for server state management and caching
- **Routing**: Wouter for lightweight client-side routing
- **Form Handling**: React Hook Form with Zod validation for type-safe form management
- **Responsive Design**: Mobile-first approach with responsive breakpoints

### Backend Architecture
The server is built with Express.js following RESTful API principles:

- **API Design**: RESTful endpoints for feedback operations (GET, POST, DELETE)
- **Data Validation**: Zod schemas for runtime type checking and validation
- **Error Handling**: Centralized error handling middleware
- **Request Logging**: Custom middleware for API request logging and performance monitoring
- **Development Setup**: Vite integration for SSR and HMR during development

### Data Storage Solutions
The application uses PostgreSQL as the primary database with Drizzle ORM for type-safe database operations:

- **Schema Design**: Single feedback table with comprehensive fields for student information, course details, ratings, and metadata
- **ORM**: Drizzle ORM provides type-safe queries and automatic TypeScript inference
- **Migrations**: Database schema versioning through Drizzle Kit
- **Development Storage**: In-memory storage implementation for development and testing

### Authentication and Authorization
Currently implements a simple role-based view system without authentication:

- **Role Switching**: Toggle between student and admin views
- **No Authentication**: System assumes trusted environment (educational institution network)
- **Future-Ready**: Architecture supports adding authentication layers

### Data Validation and Type Safety
Comprehensive type safety across the full stack:

- **Shared Types**: Common TypeScript types and Zod schemas in shared directory
- **Runtime Validation**: Server-side validation using Zod schemas
- **Client Validation**: Form validation with React Hook Form and Zod resolvers
- **Database Types**: Drizzle ORM provides compile-time type checking for database operations

## External Dependencies

### Database
- **Neon Database**: Serverless PostgreSQL database service via `@neondatabase/serverless`
- **Connection**: Environment variable `DATABASE_URL` for database connection string

### UI Components and Styling
- **Radix UI**: Comprehensive primitive component library for accessibility and functionality
- **Tailwind CSS**: Utility-first CSS framework for styling
- **Lucide React**: Icon library for consistent iconography
- **Class Variance Authority**: Utility for managing component variants

### Development and Build Tools
- **Vite**: Build tool and development server with React plugin
- **TypeScript**: Static type checking across frontend and backend
- **ESBuild**: Fast bundling for production builds
- **PostCSS**: CSS processing with Tailwind CSS integration

### Form and Validation
- **React Hook Form**: Performant form library with minimal re-renders
- **Zod**: TypeScript-first schema validation library
- **Hookform Resolvers**: Integration between React Hook Form and Zod

### State Management and Data Fetching
- **TanStack Query**: Server state management, caching, and synchronization
- **Date-fns**: Date manipulation and formatting utilities

### Runtime and Session Management
- **Connect PG Simple**: PostgreSQL session store for Express sessions (prepared for future authentication)

### Development Environment
- **Replit Integration**: Specialized plugins for Replit development environment
- **Runtime Error Overlay**: Development error handling and debugging
- **Cartographer**: Development tooling for Replit environment