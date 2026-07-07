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