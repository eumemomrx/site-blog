# Overview

This is a Next.js-based affiliate marketing platform that enables users to create and manage online stores for selling products as affiliates. The application is a modern, server-side rendered website built with Next.js 15 (using the Pages Router), React 19, and TypeScript, with a focus on fast site creation and business optimization tools.

The platform emphasizes a quick setup process (under 5 minutes) and provides users with the ability to track and optimize their online businesses without requiring credit card information to get started.

# Recent Changes

**November 8, 2025 - Vercel to Replit Migration**
- Migrated project from Vercel to Replit environment
- Updated package.json scripts to use port 5000 with 0.0.0.0 host binding for Replit compatibility
- Configured development workflow to run Next.js dev server on port 5000
- Set up deployment configuration for autoscale deployment with proper build and start commands
- All dependencies installed and app running successfully without errors

# User Preferences

Preferred communication style: Simple, everyday language.

# System Architecture

## Frontend Architecture

**Framework Choice: Next.js 15 (Pages Router)**
- **Problem**: Need for server-side rendering, static generation, and API routes in a single framework
- **Solution**: Next.js Pages Router provides file-based routing, SSR/SSG capabilities, and built-in API routes
- **Rationale**: Simplifies development with convention over configuration, excellent SEO support, and optimal performance

**UI Component System: shadcn/ui + Radix UI**
- **Problem**: Need for accessible, customizable UI components without heavy dependencies
- **Solution**: shadcn/ui components built on Radix UI primitives with Tailwind CSS styling
- **Rationale**: Copy-paste component architecture allows full customization, Radix ensures accessibility, and Tailwind provides utility-first styling

**Styling Approach: Tailwind CSS**
- **Problem**: Consistent design system with custom color palette and responsive design
- **Solution**: Tailwind CSS with custom configuration including custom colors (blue, cyan, gray variants) and container settings
- **Rationale**: Utility-first approach speeds development, custom theme maintains brand consistency, and built-in responsive utilities simplify mobile-first design

**Component Organization Pattern**
- **Problem**: Maintainable component structure with clear separation of concerns
- **Solution**: Feature-based component folders with barrel exports (index.ts files)
- **Alternatives**: Flat component structure, monolithic components
- **Pros**: Clear feature boundaries, easier imports, better code organization
- **Cons**: Slightly more boilerplate with index files

**Layout Pattern**
- **Problem**: Consistent header/footer across all pages
- **Solution**: Custom Layout component wrapping the entire application via _app.tsx
- **Rationale**: Single source of truth for site-wide layout, simplified page components

## Routing & Navigation

**Active Link Management**
- **Problem**: Visual feedback for current page in navigation
- **Solution**: Custom ActiveLink component using Next.js router to detect current path
- **Rationale**: Enhances UX by highlighting current location, reusable across navigation

**Route Structure**
- Primary routes: `/` (home), `/blog`, `/comecar` (get started), `/criar-loja` (create store)
- Legal routes: `/termos-de-uso`, `/politica-de-privacidade`, `/feedback`
- API routes: `/api/hello` (example endpoint)

## Type Safety

**TypeScript Configuration**
- **Problem**: Need for type safety across the application
- **Solution**: Strict TypeScript configuration with ES2017 target
- **Rationale**: Catches errors at compile time, improves developer experience with IntelliSense

**Path Aliases**
- **Problem**: Complex relative imports (../../components)
- **Solution**: `@/*` alias mapping to `./src/*`
- **Rationale**: Cleaner imports, easier refactoring, reduced errors

## Development Configuration

**Port Configuration**
- **Problem**: Default port conflicts or specific hosting requirements
- **Solution**: Custom port 5000 with 0.0.0.0 host binding
- **Rationale**: Allows external access (necessary for containerized/cloud environments), avoids common port conflicts

**Build Optimization**
- React Strict Mode enabled for development checks
- Incremental builds for faster compilation
- Font optimization via next/font

## Design System

**Color Palette**
- Blue scale: Primary actions and interactive elements (4 shades)
- Cyan scale: Accent and highlights (3 shades)
- Gray scale: Backgrounds and text hierarchy (8 shades)
- White: High contrast elements

**Typography**
- Primary font: PT Sans Caption (sans-serif fallback)
- Custom spacing and sizing defined through Tailwind config

**Responsive Breakpoints**
- Container max-width: 1200px at 2xl breakpoint
- Mobile-first approach with hiding/showing elements at md/lg breakpoints

# External Dependencies

## UI Framework & Utilities

- **Next.js 15.3.4**: Core framework for SSR, routing, and API routes
- **React 19**: UI library
- **TypeScript 5**: Type system
- **Tailwind CSS 3.4**: Utility-first CSS framework
- **PostCSS & Autoprefixer**: CSS processing

## Component Libraries

- **Radix UI (@radix-ui/react-slot)**: Headless UI primitives for accessibility
- **shadcn/ui**: Component collection (configured, not installed as package)
- **Lucide React**: Icon library

## Utility Libraries

- **clsx & tailwind-merge**: Class name utilities for conditional styling
- **class-variance-authority**: Component variant management

## Development Tools

- **ESLint**: Code linting with Next.js configuration
- **TypeScript Types**: @types/node, @types/react, @types/react-dom

## Asset Dependencies

- **Static Assets**: Logo and hero section SVG illustrations stored in `/public`
- **Fonts**: PT Sans Caption (likely loaded via Google Fonts or system fonts)

## Future Integration Points

The architecture suggests future integrations for:
- Authentication system (user accounts for store creation)
- Database layer (likely needed for store management, products, analytics)
- Payment processing (for premium features or affiliate transactions)
- Analytics tracking (for business optimization features mentioned in hero)
- Content management (for blog functionality referenced in navigation)