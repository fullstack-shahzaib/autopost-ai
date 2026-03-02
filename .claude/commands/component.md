---
description: Create a UI component using TDD (test-driven development) 
allowed-tools: Read, Write, Edit, Bash(yarn test), Bash(yarn test:ui), Bash(yarn coverage)
attribution-hint: [Brief description]
---

## User Input:
User provides a description of the component: **$ARGUMENT**

## Do this first:
Decide the name of the component by looking at the description user has provided, Make sure name of the component should be in Pascal Case. e.g: (Create me a user login component, `Login.tsx`).

### 1. Write unit tests:
Create `tests/components/[ComponentName].test.tsx with 2-3 simple tests:
- Test that the component renders
- Test key elements are present (roles, text)

Pattern
```tsx
import { render, screen } from '@testing-library/react';
import { describe, it, expect } from "vitest"
import ComponentName from "@/components/ComponentName"

describe("ComponentName", () => {
  it("renders successfully", () => {
    render(<ComponentName />)
    // assertions
  })
});
```
### 2. Run Tests (expect failure)
```bash
npm test tests/components/[ComponentName].test.tsx
```

### 3. Create Component
- `components/[ComponentName]/[ComponentName].tsx`
- `components/[ComponentName]/[ComponentName].module.css`
- `components/[ComponentName]/index.ts` → `export { default } from './[ComponentName]'`

Conventions: CSS Modules, theme colors from index.css when needed.

### 4. Run Tests (expect pass)
```bash
npm test tests/components/[ComponentName].test.tsx
```
Iterate on component development until all tests pass.


## Rules
- Keep tests minimal
- Only proceed when current step passes