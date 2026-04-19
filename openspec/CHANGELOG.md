# Changelog

All notable changes to this project will be documented here.
Format based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).

---

## [0.1.0] - 2026-04-19

### Added

- Initial project setup with Next.js 16.2.4, React 19, TypeScript
- Tailwind CSS v4 configured
- Prisma ORM with PostgreSQL driver adapter pattern
- Database models: Category, Product, User (DNI-based auth)
- Better Auth configured for authentication with DNI (no email)
- Auth API route at `/api/auth/[...all]`
- Database seed script with admin user and sample data
- shadcn/ui initialized with radix-sera preset
- Project structure following layered architecture (ui/application/domain/infrastructure)
- Button component as first shadcn component
- Docker Compose setup for PostgreSQL 18.3

### Features

- Admin authentication via DNI + password
- Category and Product management (schema ready)
- Mobile-first public menu display (to be implemented)
- Admin dashboard for menu management (to be implemented)

---

## [Unreleased]

### Planned

- Server Actions for CRUD operations
- Public menu page at `/menu`
- Admin pages: login, dashboard, products, categories
- Drag-and-drop reordering
- ISR for real-time menu updates
