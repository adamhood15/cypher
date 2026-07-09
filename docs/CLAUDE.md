# CLAUDE.md

## Project

This project is a Progressive Web App for a waterpark.

The application should prioritize clean architecture, maintainability, and scalability over quick fixes.

Always favor long-term solutions.

---

# Technology

Frontend

- Next.js (App Router)
- React
- TypeScript
- Tailwind CSS

Backend

- NestJS
- PostgreSQL
- Prisma

Package Manager

- npm

Version Control

- Git

---

# Coding Standards

Always:

- Use TypeScript
- Avoid `any`
- Prefer interfaces over types when appropriate
- Use async/await
- Keep functions under 50 lines when practical
- Keep components focused on one responsibility
- Write reusable components
- Create custom hooks when logic is reused
- Prefer composition over inheritance

---

# React

Prefer:

- Functional Components
- Server Components where possible
- Client Components only when necessary

Never create unnecessary re-renders.

---

# Styling

Use Tailwind CSS.

Never use inline styles.

Avoid custom CSS unless absolutely necessary.

Use utility classes first.

---

# Folder Structure

/app

/components

/features

/hooks

/lib

/services

/types

/utils

/prisma

/public

---

# API Design

REST APIs.

Keep controllers thin.

Business logic belongs in services.

Validation belongs in DTOs.

Never place business logic inside controllers.

---

# Database

Use Prisma.

Every schema change requires a migration.

Never perform raw SQL unless necessary.

---

# Security

Always validate user input.

Sanitize all user-generated content.

Protect routes requiring authentication.

Never expose secrets.

Never hardcode API keys.

---

# Performance

Lazy-load heavy components.

Optimize images.

Use server rendering when appropriate.

Minimize client JavaScript.

---

# Accessibility

All forms require labels.

Images require alt text.

Keyboard navigation must work.

Maintain sufficient color contrast.

---

# Git

Small commits.

Descriptive commit messages.

Never commit secrets.

---

# Documentation

Document:

- public functions
- exported hooks
- reusable utilities

Avoid obvious comments.

---

# Testing

When writing new functionality:

- consider edge cases
- validate user input
- ensure loading states
- ensure error states

---

# Working Style

Before making significant architectural changes:

1. Explain the reasoning.
2. Outline the implementation plan.
3. Wait for approval if the change is substantial.

When implementing features:

- Break work into small, logical steps.
- Prefer maintainable code over clever code.
- Reuse existing components and utilities whenever possible.
- If requirements are ambiguous, ask clarifying questions instead of making assumptions.

When fixing bugs:

- Identify the root cause before changing code.
- Explain why the bug occurred.
- Keep fixes as small and targeted as possible.

Always think like a senior software engineer responsible for a production application used by thousands of guests.

---

# UI Development Strategy

Before building application features, establish a reusable design system.

Build production-quality UI components that will be used throughout the application rather than creating one-off implementations.

The initial development phase should focus on creating a component library before building pages.

Core components should include:

- Buttons
- Icon Buttons
- Cards
- Page Headers
- Navigation
- Bottom Navigation
- Drawers
- Modals
- Dialogs
- Forms
- Inputs
- Selects
- Checkboxes
- Radio Buttons
- Toggles
- Tabs
- Accordions
- Badges
- Chips
- Alerts
- Toast Notifications
- Loading Indicators
- Skeleton Loaders
- Empty States
- Error States
- Event Cards
- Ride Status Cards
- Digital Pass Cards
- Promotional Banners

Each component should:

- Be reusable and composable.
- Follow accessibility best practices (WCAG 2.2 AA).
- Support light and dark themes.
- Be responsive by default.
- Be fully typed with TypeScript.
- Include sensible default variants and sizes.
- Avoid duplicated styling or logic.

When creating new pages, always reuse existing components whenever possible. If a required component does not exist, create it as a reusable component before implementing the page.

--- 

# Development Workflow

Implement work in the following order:

1. Foundation
   - Project configuration
   - Authentication
   - Database
   - Routing
   - Theme setup

2. Design System
   - Build reusable UI components
   - Establish typography
   - Establish spacing
   - Create color tokens
   - Create icon library
   - Create layout primitives

3. Core Features
   - Authentication
   - Home
   - Digital Pass
   - Events
   - Park Map
   - Notifications
   - Account

4. Integrations
   - Analytics
   - Push Notifications
   - APIs
   - Third-party services

5. Polish
   - Accessibility
   - Performance
   - Testing
   - PWA optimization

Do not skip ahead if foundational work is incomplete unless explicitly instructed.

--- 

# Architecture

Follow a feature-based architecture.

Features should be isolated whenever possible.

Example:

/features
    /authentication
    /events
    /map
    /notifications
    /passes
    /rides
    /tickets
    /user

Each feature should own:

- components
- hooks
- services
- types
- API calls
- validation

Avoid creating large shared folders unless functionality is genuinely shared.

--- 
# Design Tokens

Never hardcode colors, spacing, typography, border radius, or shadows.

Create reusable design tokens for:

- Colors
- Typography
- Border Radius
- Shadows
- Spacing
- Z-index
- Animations
- Breakpoints

All components should consume these tokens rather than defining their own values.

--- 

# State Management

Prefer the simplest solution.

Use:

- React state for local component state.
- Context only for truly global concerns.
- Server Components whenever possible.
- React Query (TanStack Query) for server state.
- URL parameters for shareable application state.

Avoid unnecessary global state.

--- 

# Error Handling

Never silently ignore errors.

Always:

- Display meaningful user-friendly messages.
- Log unexpected errors.
- Handle loading states.
- Handle empty states.
- Handle network failures.
- Handle offline mode when applicable.

Avoid generic "Something went wrong" messages.

--- 

# Component Documentation

Every reusable component should include:

- Purpose
- Props
- Variants
- Usage examples

Complex components should include inline documentation explaining important implementation decisions.

--- 


# API Standards

All API requests should:

- Use typed request and response models.
- Handle retries where appropriate.
- Support cancellation.
- Return standardized error objects.

Avoid API calls directly inside components.

Business logic belongs in services.

--- 

# Mobile Experience

Design for one-handed use.

Prioritize:

- Large touch targets (44px minimum)
- Bottom navigation
- Thumb-friendly interactions
- Minimal typing
- Fast loading

Avoid deeply nested navigation.

Every screen should be usable on a 390px-wide device.

---

# Performance Budget

Prioritize performance.

Avoid unnecessary dependencies.

Prefer native browser APIs before adding third-party packages.

Before introducing a dependency, verify that an existing solution is insufficient.

Optimize bundle size whenever possible.

---

# AI Collaboration Rules

Before writing code:

- Understand the existing codebase.
- Explain the implementation plan.
- Identify potential risks.
- Reuse existing code whenever possible.

Never rewrite working code unless requested.

Avoid introducing breaking changes.

Prefer incremental improvements over large rewrites.

When multiple implementation options exist, briefly explain the trade-offs before proceeding.

When requirements are unclear, ask questions instead of making assumptions.

--- 

# Code Review Checklist

Before considering work complete, verify:

- TypeScript has no errors.
- Linting passes.
- Build succeeds.
- No duplicated logic exists.
- Components remain reusable.
- Accessibility requirements are met.
- Responsive layouts function correctly.
- Error handling is implemented.
- Loading states are present.
- Empty states are present.

---

# Future Expansion

Design the application so additional parks can be added without architectural changes.

Avoid hardcoding:

- Park names
- Park branding
- Time zones
- Operating hours
- Events
- Maps
- Attractions
- Promotions

The application should support multiple parks through configuration and APIs.

Assume the product will eventually support multiple brands, locations, and environments.