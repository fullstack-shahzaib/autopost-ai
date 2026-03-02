# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

- **Dev server:** `yarn dev`
- **Production build:** `yarn build` (runs `tsc -b` then `vite build`)
- **Lint:** `yarn lint`
- **Preview build:** `yarn preview`

> Use `yarn` (not npm) — the project uses Yarn with node-modules linker (`.yarnrc.yml`).

## Architecture

This is a **Vite + React 19 + TypeScript** SPA.

**Entry flow:**
```
index.html → src/main.tsx → src/App.tsx
```

- `src/main.tsx` — mounts `<App />` into `#root` with React StrictMode
- `src/App.tsx` — main application component
- `src/index.css` — global styles (theming, typography, light/dark mode)
- `src/App.css` — component-scoped styles

**TypeScript config:**
- Strict mode enabled; unused locals/parameters are errors
- Target: ES2022, JSX transform: `react-jsx`
- `tsconfig.json` references both `tsconfig.app.json` (app code) and `tsconfig.node.json` (build tooling)

**ESLint** uses flat config (`eslint.config.js`) with TypeScript-ESLint, React Hooks, and React Refresh rules.
