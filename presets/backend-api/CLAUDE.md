# Backend API Development Guidelines

Configuration for TypeScript/Node.js REST API development.

## Tech Stack

- **Runtime**: Node.js 20+
- **Framework**: Hono (lightweight, fast HTTP framework)
- **Database**: ArangoDB (graph + document database)
- **Validation**: Zod (schema validation)
- **Testing**: Vitest

## Architecture Patterns

### Project Structure
```
src/
  modules/           # Feature modules
    users/
      handlers/      # HTTP handlers
      services/      # Business logic
      types.ts       # TypeScript types
      routes.ts      # Route definitions
  core/              # Shared utilities
  index.ts           # App entry point
```

### API Response Format
Always return consistent JSON responses:
```typescript
// Success
{ "success": true, "data": { ... } }

// Error
{ "success": false, "error": { "code": "ERROR_CODE", "message": "..." } }
```

## Coding Standards

### Request Validation
Always validate incoming requests with Zod:
```typescript
const CreateUserSchema = z.object({
  email: z.string().email(),
  name: z.string().min(1).max(100),
});
```

### Error Handling
- Use custom error classes for business errors
- Log errors with context (userId, requestId)
- Never expose internal errors to clients

### Database Queries
- Use parameterized queries (never string interpolation)
- Implement pagination for list endpoints
- Add appropriate indexes for query patterns

## Performance

- Use connection pooling for database
- Implement caching for frequently accessed data
- Add request timeout handling
