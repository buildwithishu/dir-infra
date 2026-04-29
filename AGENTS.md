# Repository Guidelines

## Project Structure & Module Organization

This repository is a static landing page deployment. The primary editable page is `index.html`, which contains the markup and embedded CSS for the Root Space coworking site. `vercel.json` configures the deployed root route. The directory `FIND Real Estate _ Purchase, Rent or Sell Commercial and Residential Real Estate_files/` contains imported reference assets, scripts, styles, images, and media used by the page. `drive-assets/` stores source media from Drive. Generated Playwright captures and ad hoc screenshots are ignored by `.gitignore`; do not commit new `*.png` files unless the ignore rule is intentionally changed.

## Build, Test, and Development Commands

There is no package-managed build step. Preview the site with a local static server:

```bash
python3 -m http.server 8000
```

Then open `http://localhost:8000/index.html`. For a Vercel-like route check, install/use Vercel CLI outside this repo workflow only when needed:

```bash
vercel dev
```

Use `git status --short --branch` before and after edits to confirm the intended files changed.

## Coding Style & Naming Conventions

Keep `index.html` readable and self-contained: two-space indentation, lowercase HTML tags, semantic class names, and CSS custom properties in `:root` for shared colors or asset paths. Prefer descriptive section classes such as `.site-header`, `.hero`, and `.benefits-grid`. Keep asset references relative, and preserve spaces in existing imported asset paths unless moving all references together.

## Testing Guidelines

No automated test framework is configured. Manually verify changes in a browser at desktop and mobile widths. Check the fixed header, hero layout, scroll behavior, images, and contact/navigation links. When visual behavior changes, use Playwright or browser screenshots locally, but avoid committing generated captures.

## Commit & Pull Request Guidelines

Recent history uses short conventional-style commits, for example `feat: update Root Space landing page`, `fix: update hero coworking copy`, and `chore: add vercel static hosting config`. Continue using `feat:`, `fix:`, `chore:`, `docs:`, or `refactor:` with an imperative summary. Pull requests should include a concise description, list changed user-facing sections, mention manual browser checks, and include screenshots only when they are necessary for review.

## Security & Configuration Tips

Do not commit secrets, analytics credentials, or private customer data. Keep deployment configuration in `vercel.json` minimal and review route rewrites carefully because they affect the production entry point.
