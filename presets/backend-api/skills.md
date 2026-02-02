# Backend API Skills

Custom slash commands for backend development.

## /api-scaffold

Creates a new API module with standard structure.

**Usage**: `/api-scaffold <module-name>`

**Example**: `/api-scaffold products`

Creates:
- `src/modules/products/handlers/`
- `src/modules/products/services/`
- `src/modules/products/types.ts`
- `src/modules/products/routes.ts`

---

## /test-api

Runs API integration tests with coverage.

**Usage**: `/test-api [module]`

**Commands**:
```bash
# Run all tests
pnpm test

# Run specific module tests
pnpm test src/modules/<module>
```

---

## /db-migrate

Run database migrations.

**Usage**: `/db-migrate [up|down|status]`

**Commands**:
```bash
pnpm db:migrate:up
pnpm db:migrate:down
pnpm db:migrate:status
```

---

## /deploy-staging

Deploy to staging environment.

**Usage**: `/deploy-staging`

**Pre-checks**:
1. All tests pass
2. No TypeScript errors
3. Build succeeds

**Command**: `pnpm deploy:staging`
