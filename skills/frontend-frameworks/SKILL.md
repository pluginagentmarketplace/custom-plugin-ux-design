---
name: frontend-frameworks
description: Master modern frontend frameworks including React, Vue, and Angular. Learn component architecture, hooks, lifecycle management, performance optimization, and best practices for building scalable web applications.
---

# Frontend Frameworks

## Quick Start

Choose your framework and dive in:

### React Fundamentals
```javascript
import React, { useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}
```

### Vue 3 Composition API
```javascript
import { ref } from 'vue';

export default {
  setup() {
    const count = ref(0);

    return {
      count,
      increment: () => count.value++
    };
  }
}
```

## Framework Comparison

| Aspect | React | Vue | Angular |
|--------|-------|-----|---------|
| Learning Curve | Medium | Easy | Steep |
| Bundle Size | 42KB | 33KB | 150KB |
| State Management | Redux, Zustand | Vuex, Pinia | NgRx |
| Best For | Large apps | Progressive | Enterprise |
| Performance | Excellent | Excellent | Good |

## Key Topics

### React Advanced Patterns
- Custom hooks for code reuse
- Context API for state management
- React.memo & useMemo optimization
- Error boundaries for error handling
- Suspense for code splitting
- Concurrent rendering features

### Vue 3 Composition API
- Reactive refs & computed properties
- Watch & watchEffect reactivity
- Lifecycle hooks in composition API
- Component composition patterns
- Teleport & Fragment features

### Angular Enterprise Features
- Dependency injection & services
- RxJS observables & operators
- Decorators & metadata
- Guards & resolvers
- Advanced routing
- Change detection strategies

## Best Practices

1. **Component Design**
   - Single Responsibility Principle
   - Reusable component libraries
   - Props down, events up pattern
   - Composition over inheritance

2. **Performance**
   - Code splitting & lazy loading
   - Image optimization
   - Memoization strategies
   - Bundle analysis

3. **State Management**
   - When to use local vs global state
   - Avoiding prop drilling
   - Immutable state patterns
   - Time-travel debugging

4. **Testing**
   - Unit tests with Jest/Vitest
   - Component testing with React Testing Library
   - E2E testing with Cypress/Playwright
   - Snapshot testing considerations

## Advanced Resources

- React: https://react.dev
- Vue: https://vuejs.org
- Angular: https://angular.io

## Related Skills

- css-styling - Styling frameworks and methodologies
- state-management - Advanced state management patterns
- web-accessibility - WCAG and accessibility testing
