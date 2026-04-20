# Guia de Contribucion

## Objetivo

Este proyecto usa el ecosistema [Gentleman AI](https://github.com/Gentleman-Programming/gentle-ai). Su uso es obligatorio para mantener consistencia de convenciones, codigo y documentacion.

## Reglas Criticas

### Git

- Nunca ejecutar `git reset` (hard, soft o mixed) sin permiso explicito.
- Nunca ejecutar `git rebase -i` sin permiso explicito.
- Antes de cualquier operacion destructiva: detenerse y preguntar.

### Review

Rechazar cambios si hay:

- Secrets o credenciales hardcodeadas.
- `console.log` en codigo de produccion.
- Falta de manejo de errores.

## Flujo de contribucion

1. Crear branch desde `main`.
2. Implementar la feature/fix.
3. Correr checks y validar cambios.
4. Commitear usando Conventional Commits.
5. Push de branch remoto.
6. Abrir PR a `main`.
7. Resolver review y mergear.

### Comandos del flujo

```bash
git checkout -b feature/nombre
git commit -m "feat: descripcion"
git push -u origin feature/nombre
```

## Convencion de commits

| Tipo | Uso |
|------|-----|
| `feat:` | Nueva funcionalidad |
| `fix:` | Correccion de bug |
| `docs:` | Documentacion |
| `style:` | Formato sin cambios funcionales |
| `refactor:` | Refactor |
| `test:` | Tests |
| `chore:` | Mantenimiento |

## Pre-commit (GGA)

Instalar el hook de GGA para validar convenciones y calidad antes de cada commit.

Nota: en Windows, usar WSL o Git Bash (no PowerShell/CMD) para este flujo.

```bash
gga install
# Editar .gga para configurar PROVIDER
# Crear/actualizar AGENTS.md con estandares del proyecto
```

Mas informacion: [GGA Documentation](https://github.com/Gentleman-Programming/gentleman-guardian-angel).

## Pull Requests

- Titulo claro siguiendo Conventional Commits.
- Descripcion del que y por que.
- Link al issue (si aplica).
- Screenshots para cambios de UI.

## SDD (Spec-Driven Development)

Para features significativas, usar:

```text
/sdd-init
/sdd-propose <change>
/sdd-spec <change>
/sdd-design <change>
/sdd-tasks <change>
/sdd-apply <change>
/sdd-verify <change>
/sdd-archive <change>
```

## Estandares de codigo

- Solo function components.
- Server Components por defecto; Client Components solo con `"use client"`.
- TypeScript en strict mode.
- Sin `console.log` en produccion.
- Manejo de errores obligatorio.
- Mensajes de error en espanol.

## UI Components

Usar shadcn/ui para componentes base.

```bash
npx shadcn@latest add <componente>
```

## Base de datos

```bash
npm run db:migrate
npm run db:seed
npm run db:studio
npx prisma generate
```

## Memorias (Engram)

Sincronizar memorias al iniciar y cerrar trabajo:

```bash
engram sync --import
engram sync
```

Primero ejecutar `engram sync --import` para traer contexto. Al final, ejecutar `engram sync` para exportar nuevas memorias del trabajo.

Mas informacion: [Engram Documentation](https://github.com/Gentleman-Programming/engram#quick-start).

## Stack de referencia

| Tecnologia | Version |
|------------|---------|
| Next.js | 16.2.4 |
| React | 19.2.4 |
| TypeScript | 5 |
| Tailwind CSS | 4 |
| Prisma | 7.7.0 |
| better-auth | 1.6.5 |
| shadcn | 4.3.0 |