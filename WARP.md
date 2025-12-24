# WARP.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## Commands

```bash
pnpm install        # install deps
pnpm dev            # dev server at localhost:4321
pnpm build          # build to ./dist/
pnpm astro check    # type check
```

## Architecture

Astro 5 static site for an advent calendar of Warp tips.

### Content System
- `src/content/days/*.md` - 25 markdown files (01.md-25.md) with frontmatter `url` field linking to external content
- `src/content.config.ts` - Astro content collection using glob loader with zod schema

### Pages
- `src/pages/index.astro` - single-page app with:
  - Hardcoded drawer positions from Figma (pixel coords → percentages)
  - View Transitions API for letter-to-modal morph animation
  - Modal dialog populated from pre-rendered markdown content

### Assets
- `public/assets/drawers/day-*.png` - 25 drawer images
- `public/assets/drawers/letter.png` - shared letter envelope
- `public/assets/winter-bg.png`, `wood-texture.png`, `letter-texture.png` - textures

### Fonts
Custom fonts via @fontsource: Instrument Serif (headers), Gelasio (body).
