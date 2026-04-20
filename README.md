# Menu QR Admin

v0.1.0 - Next.js 16 + React 19 + TypeScript + Tailwind v4 + Prisma + PostgreSQL

Sistema web de gestion de menu con QR para cafeteria. Los administradores gestionan categorias y productos; los usuarios finales visualizan el menu escaneando un QR.

## Stack

| Capa | Tecnologia |
|------|------------|
| Framework | Next.js 16.2.4 + React 19.2.4 |
| Estilos | Tailwind CSS v4 + shadcn/ui |
| ORM / DB | Prisma 7.7.0 + PostgreSQL |
| Auth | better-auth 1.6.5 (login con DNI) |

## Requisitos

- Node.js 20+
- npm 10+
- Docker (para levantar PostgreSQL local)

## Setup local

```bash
npm install
cp .env.example .env
docker-compose up -d
npm run db:migrate
npm run db:seed
npm run dev
```

Aplicacion disponible en http://localhost:3000.

## Variables de entorno

```env
DATABASE_URL="postgresql://qr_admin:qr_password@localhost:5432/menu_qr_admin"
BETTER_AUTH_SECRET="min-32-chars"
BETTER_AUTH_URL="http://localhost:3000"
SEED_ADMIN_DNI_1="12345678"
SEED_ADMIN_PASSWORD_1="admin123"
```

## Scripts

| Script | Descripcion |
|--------|-------------|
| npm run dev | Inicia entorno de desarrollo |
| npm run build | Compila la app para produccion |
| npm run start | Ejecuta build de produccion |
| npm run lint | Ejecuta ESLint |
| npm run db:migrate | Ejecuta migraciones de Prisma |
| npm run db:seed | Carga datos semilla |
| npm run db:studio | Abre Prisma Studio |
| npm run test | Ejecuta tests una vez |
| npm run test:watch | Ejecuta tests en modo watch |
| npm run test:coverage | Ejecuta tests con cobertura |

## Modelo de datos

```text
Category (name, order)
└── Product (name, price, available, order)

User (dni, password, role)
```

El campo `order` en `Category` y `Product` define el orden de visualizacion.

## Estructura del proyecto

```text
prisma/
├── schema.prisma
├── seed.ts
└── migrations/

src/
├── app/
│   ├── api/auth/[...all]/route.ts
│   ├── globals.css
│   ├── layout.tsx
│   └── page.tsx
├── components/ui/
│   └── button.tsx
├── lib/
│   ├── auth-client.ts
│   ├── auth.ts
│   ├── prisma.ts
│   └── utils.ts
└── __tests__/
    ├── auth.test.ts
    └── utils.test.ts
```

## Troubleshooting

- Prisma out of sync:

  ```bash
  npx prisma generate
  ```

- Auth no funciona:
  Verificar que `BETTER_AUTH_URL` coincida exactamente con la URL (sin slash final).

- DB no conecta:
  Verificar `DATABASE_URL` y el contenedor con:

  ```bash
  docker-compose ps
  ```

## Contribucion

Ver [CONTRIBUTING.md](CONTRIBUTING.md).
