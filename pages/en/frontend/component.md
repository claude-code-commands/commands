---
description: Generate React components with TypeScript definitions
allowed-tools: Read, Edit, Write, Bash(npm:*)
---

## Your task

Generate React components with proper TypeScript definitions, following best practices for modern React development.

### Component Creation Process

1. **Analyze Requirements**: Review the component specification and requirements
2. **Create Component Structure**: Generate the main component file with proper imports and exports
3. **Add TypeScript Definitions**: Create comprehensive type definitions for props and state
4. **Generate Tests**: Create unit tests for the component using Jest and React Testing Library
5. **Add Storybook Stories**: Create Storybook stories for component documentation
6. **Update Exports**: Add the component to the appropriate index files

### Implementation Guidelines

- Use functional components with hooks
- Follow React naming conventions
- Implement proper error boundaries where needed
- Add accessibility attributes (ARIA labels, roles)
- Include PropTypes for runtime validation
- Use CSS modules or styled-components for styling
- Follow the project's existing code style and patterns

### Example Component Structure

```tsx
import React from 'react';
import { ComponentProps } from './types';

export const MyComponent: React.FC<ComponentProps> = ({
  title,
  children,
  variant = 'default',
  ...props
}) => {
  return (
    <div className={`component component--${variant}`} {...props}>
      <h2>{title}</h2>
      {children}
    </div>
  );
};
```

This command helps create consistent, well-structured React components that follow modern development practices.