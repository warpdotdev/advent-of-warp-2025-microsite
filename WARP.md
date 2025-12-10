# WARP.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## Project Overview

**astro-tailwind** is a minimal Astro starter template with integrated Tailwind CSS v4 for styling.

## Quick Commands

| Command | Purpose |
|---------|---------|
| `pnpm dev` | Start local dev server (localhost:4321) |
| `pnpm build` | Build production site to `./dist/` |
| `pnpm preview` | Preview production build locally |
| `pnpm astro check` | Check for type errors and validate config |
| `pnpm astro add <integration>` | Add new Astro integrations |

## Architecture

### Project Structure

```
src/
├── pages/          # Route pages (*.astro, *.md files become routes)
├── styles/         # Global stylesheets (global.css imports Tailwind)
└── components/     # Reusable Astro/React/Vue/Svelte components (optional)

public/            # Static assets (images, fonts, etc.)
```

### Key Configurations

- **Astro Config** (`astro.config.mjs`): Sets up Tailwind CSS via `@tailwindcss/vite` plugin
- **TypeScript** (`tsconfig.json`): Uses strict Astro preset, includes type generation in `.astro/types.d.ts`
- **Styling**: Tailwind CSS v4 imported in `src/styles/global.css` and applied globally

## Development Notes

- Pages in `src/pages/` automatically become routes based on filename
- Astro uses file-based routing (e.g., `src/pages/about.astro` → `/about/`)
- Tailwind CSS is configured via Vite integration and applies globally
- Use `pnpm` for package management (per user rules)
- The project uses ES modules (`"type": "module"` in package.json)

## Debugging

- Use `pnpm astro check` to validate Astro files and catch type/configuration errors
- Dev server rebuilds on file changes
- Check `.astro/types.d.ts` for auto-generated type definitions (commit-safe, regenerated automatically)
