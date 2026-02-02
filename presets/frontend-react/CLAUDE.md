# Frontend React Development Guidelines

Configuration for React/TypeScript frontend development.

## Tech Stack

- **Framework**: React 18+ with TypeScript
- **Build Tool**: Vite
- **Styling**: TailwindCSS
- **State**: React Query for server state, Zustand for client state
- **Testing**: Vitest + React Testing Library

## Project Structure

```
src/
  components/        # Reusable UI components
    ui/              # Base components (Button, Input, Card)
    layout/          # Layout components (Sidebar, Header)
  screens/           # Page-level components
  hooks/             # Custom React hooks
  lib/               # Utilities and helpers
  types/             # Shared TypeScript types
  App.tsx            # Root component
  main.tsx           # Entry point
```

## Component Guidelines

### Naming Conventions
- Components: PascalCase (`UserProfile.tsx`)
- Hooks: camelCase with `use` prefix (`useUserData.ts`)
- Utilities: camelCase (`formatDate.ts`)

### Component Structure
```typescript
// 1. Imports
import { useState } from 'react';

// 2. Types
interface Props {
  userId: string;
  onSelect?: (id: string) => void;
}

// 3. Component
export function UserCard({ userId, onSelect }: Props) {
  // hooks first
  const [isOpen, setIsOpen] = useState(false);

  // handlers
  const handleClick = () => { ... };

  // render
  return ( ... );
}
```

## Styling with Tailwind

- Use Tailwind utility classes directly
- Extract repeated patterns to components, not CSS
- Use `cn()` helper for conditional classes
- Follow mobile-first responsive design

## State Management

- **Server state**: Use React Query for API data
- **Client state**: Use Zustand for UI state
- **Form state**: Use React Hook Form
- Avoid prop drilling - use context or state management

## Accessibility

- Use semantic HTML elements
- Add ARIA labels where needed
- Ensure keyboard navigation works
- Test with screen readers
