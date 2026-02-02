# FlowMaster Global Standards

These standards apply to ALL projects in the organization.

## Code Quality

- **TypeScript First**: Use TypeScript for all new code
- **Strict Mode**: Enable strict TypeScript checks
- **ESLint**: Follow ESLint rules without disabling
- **Prettier**: Format code consistently

## Testing Requirements

- Write unit tests for business logic
- Aim for 80%+ code coverage on new code
- Use descriptive test names: `test_should_reject_invalid_email`

## Git Workflow

- Use conventional commits: `feat:`, `fix:`, `docs:`, `refactor:`
- Keep commits atomic and focused
- Write meaningful commit messages
- Never commit secrets or credentials

## Security

- Never hardcode API keys or passwords
- Validate all user inputs
- Use parameterized queries for database operations
- Follow OWASP security guidelines

## Documentation

- Document public APIs with JSDoc/TSDoc
- Keep README files up to date
- Comment complex business logic (explain WHY, not WHAT)
