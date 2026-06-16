# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
npm run dev       # start dev server with HMR
npm run build     # type-check then bundle for production (tsc -b && vite build)
npm run lint      # run ESLint
npm run preview   # serve the production build locally
```

## Architecture

This is a minimal React 19 + Vite 8 + TypeScript starter. The entire app lives in `src/`:

- `main.tsx` — mounts `<App />` into `#root`
- `App.tsx` — single root component; all UI lives here for now
- `App.css` / `index.css` — component and global styles respectively

Static assets used as SVG sprite sheet (`public/icons.svg`) are referenced via `<use href="/icons.svg#...">` — add new icons there rather than inlining SVGs in components.

TypeScript is split across three tsconfig files: `tsconfig.json` (project references root), `tsconfig.app.json` (browser/React code), and `tsconfig.node.json` (Vite config).
