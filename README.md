# Identity Service

Part of the [SPARK AI](https://github.com/Milir-org/spark-ai) marketing command centre — an enterprise-grade AI-powered B2B marketing suite.

## Overview

Microservice responsible for `/api/auth, /api/users`.

Runs on port **8088** and is proxied through the API gateway at `/api`.

## Quick start

```bash
# Install dependencies (pnpm recommended)
pnpm install

# Set required env vars
export DATABASE_URL="postgresql://..."

# Build and start
pnpm run build
pnpm run start

# Development (build + start with auto-restart)
pnpm run dev
```

## Structure

```
src/
  index.ts        — Entry point
  app.ts          — Express app setup
  lib/logger.ts   — Pino logger
  routes/index.ts — Route handlers
lib/db/           — Vendored @workspace/db (Drizzle ORM + schema)
```

## Environment variables

| Variable | Required | Description |
|---|---|---|
| `DATABASE_URL` | ✅ | PostgreSQL connection string |
| `PORT` | optional | HTTP port (default 8088) |
| `NODE_ENV` | optional | `development` or `production` |

## Part of the monorepo

The canonical source lives in the [spark-ai monorepo](https://github.com/Milir-org/spark-ai) under `artifacts/identity-service/`. This repo is an extracted, self-contained mirror.
