# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```sh
npm run dev       # dev server at localhost:4321
npm run build     # production build to ./dist/
npm run preview   # preview the production build locally
npx astro check  # TypeScript + Astro diagnostics
```

No test runner or linter is configured.

## Architecture

Personal portfolio site built with **Astro 6** (basics template). Deployed to Vercel via git push to `main`.

- `src/layouts/Layout.astro` — base HTML shell; all pages use this via `<slot />`
- `src/pages/index.astro` — sole page; self-contained with its own `<script>` and `<style>` blocks
- `src/components/Welcome.astro` — exists but is not currently used anywhere
- `public/` — static assets served at root (favicons)

The homepage uses a vanilla JS `requestAnimationFrame` loop directly in the page's `<script>` block to animate a blurred "ambient orb" that drifts with randomized velocity perturbation. Styles are scoped per-component via Astro's default CSS scoping.

No integrations (React, Tailwind, etc.) are configured in `astro.config.mjs` — the site is currently pure `.astro` components.
