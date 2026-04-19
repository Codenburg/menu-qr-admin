# Menu QR Admin

v0.1.0 · Next.js 16 + React 19 + TypeScript + Tailwind v4 + Prisma + PostgreSQL

Sistema web de gestión de menú con QR para cafetería. Administradores crean y editen productos organizados por categorías, usuarios públicos las visualizan escaneando un QR.

## Stack

| Capa | Tech |
|------|------|
| Framework | Next.js 16.2.4 + React 19.2.4 |
| Estilos | Tailwind CSS v4 + shadcn/ui |
| ORM / DB | Prisma v7 + PostgreSQL 18 |
| Auth | Better Auth v1 (login con DNI) |

## Setup

```bash
npm install
cp .env.example .env        # configurar DATABASE_URL y BETTER_AUTH_SECRET
docker-compose up -d        # iniciar PostgreSQL
npm run db:migrate
npm run db:seed             # opcional
npm run dev                 # puerto 3000
```

## Variables de entorno

```
DATABASE_URL="postgresql://qr_admin:qr_password@localhost:5432/menu_qr_admin"
BETTER_AUTH_SECRET="min-32-chars"
BETTER_AUTH_URL="http://localhost:3000"
SEED_ADMIN_DNI_1="12345678"
SEED_ADMIN_PASSWORD_1="admin123"
```

## Scripts

```bash
npm run dev / build / start
npm run db:migrate / db:seed / db:studio
npm run lint
```

## Modelo de datos

```
Category (nombre, orden)
└── Product (nombre, price, available, orden)

User (dni, password, role)
```

## Estructura

```
src/
├── app/
│   ├── (admin)/admin/      # dashboard, productos, categorías
│   ├── (public)/menu/      # menú público (QR target)
│   └── actions/            # Server Actions
├── components/
│   └── ui/                 # shadcn/ui
├── lib/
│   ├── prisma.ts           # Prisma client
│   ├── auth.ts             # Better Auth
│   └── utils.ts            # Utilities
└── generated/prisma/       # Prisma generated client
```

## Admin Login

- URL: `/admin/login`
- DNI: `12345678` (default seed)
- Password: `admin123`

## Troubleshooting

**Prisma out of sync** → `npm run db:generate`

**Auth no funciona** → verificar que `BETTER_AUTH_URL` coincida exactamente con la URL (sin slash final)

**DB no conecta** → verificar `DATABASE_URL` y que el contenedor Docker esté corriendo (`docker-compose ps`)

## Contribución

Ver [CONTRIBUTING.md](CONTRIBUTING.md)
