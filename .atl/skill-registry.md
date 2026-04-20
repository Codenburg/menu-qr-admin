# Skill Registry

**Project**: menu-qr-admin
**Updated**: 2026-04-20
**Mode**: hybrid (openspec + engram)

---

## Project Skills (from AGENTS.md)

These skills are loaded based on context when working in this project:

| Context | Skill |
|--------|-------|
| React | `~/skills/react-19/SKILL.md` |
| Next.js | `~/skills/nextjs-best-practices/SKILL.md` |
| TypeScript | `~/skills/typescript/SKILL.md` |
| Tailwind CSS | `~/skills/tailwind-design-system/SKILL.md` |
| Prisma | `~/skills/prisma/SKILL.md` |
| Prisma + PostgreSQL setup | `~/skills/prisma-database-setup/SKILL.md` |
| PostgreSQL | `~/skills/postgresql-best-practices/SKILL.md` |
| zod validation | `~/skills/zod-4/SKILL.md` |
| Zustand state | `~/skills/zustand-5/SKILL.md` |
| Frontend design | `~/skills/frontend-design/SKILL.md` |
| Authentication | `~/skills/better-auth-best-practices/SKILL.md` |
| Server-side auth (Next.js) | `/skills/nextjs-auth-server-side/SKILL.md` |
| Username/DNI login | `~/skills/better-auth-username/SKILL.md` |
| Forms | `~/skills/react-hook-form/SKILL.md` |
| shadcn UI | `~/skills/shadcn/SKILL.md` |
| README maintenance | `/skills/readme-guardian/SKILL.md` |
| Testing/debugging | `~/skills/testing-debugging/SKILL.md` |
| API testing | `~/skills/api-testing-patterns/SKILL.md` |

## SDD Skills

| Skill | Purpose |
|-------|---------|
| `sdd-init` | Initialize SDD context |
| `sdd-explore` | Investigate ideas before committing |
| `sdd-propose` | Create change proposal |
| `sdd-spec` | Write specifications |
| `sdd-design` | Create technical design |
| `sdd-tasks` | Break down into tasks |
| `sdd-apply` | Implement tasks |
| `sdd-verify` | Validate implementation |
| `sdd-archive` | Sync and archive completed change |

## Agent Skills

| Skill | Purpose |
|-------|---------|
| `skill-registry` | Create/update skill registry |
| `branch-pr` | PR creation workflow |
| `issue-creation` | Issue creation workflow |
| `judgment-day` | Adversarial review protocol |

## Project Conventions

- **Architecture**: Layered (UI → Application → Domain → Infrastructure)
- **Auth**: Better Auth with DNI (no email)
- **Database**: Prisma with driver adapter pattern (@prisma/adapter-pg)
- **Dev server**: Port 3000 (mandatory)
- **Error handling**: `{ data, error }` pattern, no throws for recoverable errors

### Naming
- Components: PascalCase
- Hooks: `use` + CamelCase
- Files: kebab-case
- Variables: camelCase
- Types: PascalCase
- Constants: UPPER_SNAKE_CASE

### Constraints
- UI MUST NOT access database directly
- Domain MUST NOT depend on UI
- Services orchestrate logic, don't contain business rules
- Server components by default
- MUST validate input server-side

## Notes

- Some skills referenced in AGENTS.md are listed as "Not installed" (frontend-design, postgresql-best-practices, api-testing-patterns) — these should be installed for full coverage.
- Project already has `openspec/` directory with full config, PRD, roadmap.
- Engram manifest detected (2 chunks, 11 memories across sessions).