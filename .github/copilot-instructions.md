# Copilot Coding Agent Instructions for nenoarisma-space-svelte

## Project Overview

This is a Svelte + TypeScript + Vite project, structured for rapid prototyping and easy migration to SvelteKit if needed. The codebase is minimal, focusing on core Svelte/Vite features and developer experience (HMR, intellisense).

## Architecture & Key Files

- **src/**: Main source directory
  - **main.ts**: Vite entry point, bootstraps the Svelte app
  - **App.svelte**: Root component
  - **components/**: UI components (e.g., `header.svelte`, `hero.svelte`, `about.svelte`)
  - **assets/**: Static assets (SVGs, images)
  - **app.css**: Global styles
- **public/**: Static files served directly
- **vite.config.ts**: Vite configuration (plugins, aliases)
- **svelte.config.js**: Svelte-specific config
- **tsconfig\*.json**: TypeScript configuration

## Developer Workflows

- **Build**: `bun run build` or `npm run build` (if using npm)
- **Dev Server**: `bun run dev` or `npm run dev`
- **HMR**: Hot Module Replacement is enabled, but local component state is NOT preserved by default. Use Svelte stores for persistent state.
- **Type Checking**: TypeScript is enabled; `.svelte` files support both JS and TS syntax.

## Patterns & Conventions

- **Component Structure**: Svelte components are in `src/components/`, named in lowercase (e.g., `header.svelte`).
- **State Management**: Use Svelte stores (`import { writable } from 'svelte/store'`) for shared or persistent state. Example in README.
- **Routing**: No built-in routing; add your own if needed.
- **Assets**: Place images and SVGs in `src/assets/` or `public/` for static serving.
- **TypeScript**: Mixed JS/TS is allowed in `.svelte` files. `allowJs` is enabled for flexibility.
- **Recommended Extensions**: See `.vscode/extensions.json` (if present) for VS Code setup.

## External Dependencies

- **Svelte**: UI framework
- **Vite**: Build tool
- **bun**: Alternative package manager (if present)

## Integration Points

- **Vite Plugins**: Configured in `vite.config.ts` (e.g., `@sveltejs/vite-plugin-svelte`)
- **Global Types**: Use `global.d.ts` for workspace-wide type info

## Examples

- **Persistent State**:
  ```ts
  // src/store.ts
  import { writable } from "svelte/store";
  export default writable(0);
  ```
- **Component Import**:
  ```svelte
  <script lang="ts">
    import Header from './components/header.svelte';
  </script>
  <Header />
  ```

## Migration

- The structure is similar to SvelteKit for easy migration.

---

If any conventions or workflows are unclear or missing, please provide feedback to improve these instructions.
