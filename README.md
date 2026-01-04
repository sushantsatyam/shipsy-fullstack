# shipsy-fullstack

This repository provides a clean full‑stack foundation for building a modern logistics management platform inspired by the Shipsy portal.  The stack uses **Next.js 14** for the frontend application and **NestJS** for the backend API, with **Prisma** as the ORM and **PostgreSQL** as the relational database.  A `docker-compose.yml` file is included to simplify local development by bringing up a Postgres database.

## Structure

```
shipsy-fullstack/
├── apps/
│   ├── web/                 # Next.js application
│   │   ├── pages/
│   │   │   └── index.tsx    # Example landing page
│   │   ├── next.config.js
│   │   ├── package.json
│   │   └── tsconfig.json
│   └── api/                 # NestJS backend service
│       ├── src/
│       │   ├── main.ts
│       │   ├── app.module.ts
│       │   ├── app.controller.ts
│       │   └── app.service.ts
│       ├── package.json
│       └── tsconfig.json
├── prisma/
│   └── schema.prisma        # Prisma schema
├── docker-compose.yml       # Local development services
└── .gitignore
```

## How to use

1. **Install dependencies**
   
   ```bash
   cd apps/web
   npm install
   cd ../api
   npm install
   ```

2. **Run Postgres via Docker Compose**

   ```bash
   docker compose up -d
   ```

3. **Start the backend API**

   ```bash
   cd apps/api
   npm run start:dev
   ```

4. **Start the frontend**

   ```bash
   cd apps/web
   npm run dev
   ```

5. **Generate Prisma client**

   After editing `schema.prisma`, run:

   ```bash
   npx prisma migrate dev
   npx prisma generate
   ```

This scaffold is intentionally minimal—feel free to expand it with additional modules, services, and pages based on your feature plan.
