# CLAUDE.md

Guidance for Claude Code when working in this repository. Auto-loaded on session start.

## Project

SEO landing pages for **CarbonConstruct™** — carbon reporting software for Australian construction teams. Three hand-built static HTML pages, deployed to Vercel at `carbonconstruct.online` (and the `*.vercel.app` preview domain).

## Stack

- Vanilla HTML5, **inline `<style>`** — no external CSS file.
- Google Fonts (via `<link>`) for typography; no other external assets.
- **No JS bundle.** No framework (no React, Vue, Svelte, Astro, Next, etc.).
- **No build step.** `public/` is served as-is.
- Vercel for hosting; `vercel.json` controls routing + security headers.

## Layout

```
public/
├── index.html                                     # Hub / landing (`/`)
├── carbon-reporting-software.html                 # `/carbon-reporting-software`
├── construction-carbon-reporting-software.html    # `/construction-carbon-reporting-software`
├── robots.txt
└── sitemap.xml
vercel.json                                        # cleanUrls, security headers, cache-control
package.json                                       # only `dev` (serve) and `build` (no-op)
```

## Dev & deploy

- **Local:** `npm run dev` → http://localhost:3000 (uses `npx serve public`).
- **Deploy:** auto-deploys on push to `main` via Vercel Git integration. Project `carbonconstruct-seo-pages` in team `stvn101-projects`.

## Performance targets

- **Sub-1s LCP** on 4G.
- **100 Lighthouse SEO** score.
- Keep the critical path tiny: no JS, no external CSS, inline everything that's above the fold.

## Do

- Preserve every existing `<meta>`, Open Graph (`og:*`), Twitter Card (`twitter:*`), and `application/ld+json` schema.org block on each page.
- Keep all CSS inline in `<style>` tags in `<head>`.
- Update `public/sitemap.xml` whenever a route is added, removed, or renamed.
- Keep the security headers in `vercel.json` intact (`X-Content-Type-Options`, `X-Frame-Options`, `Referrer-Policy`, `Permissions-Policy`).
- Test the golden path in a browser at `http://localhost:3000` before committing visual changes.

## Don't

- Don't introduce frameworks or bundlers (React, Vite, Tailwind CLI, PostCSS, Webpack, etc.).
- Don't add external JS or inline `<script>` unless the user explicitly asks — it breaks the performance target.
- Don't touch the main **`carbonconstruct.com.au`** platform. It lives in a separate Lovable + Supabase repo and must not be wired into this Vercel project.
- Don't weaken CSP / security headers in `vercel.json`.
- Don't fabricate new numeric or compliance claims in copy.

## Content claims (audit-grounded — do not invent new ones)

- 5,200+ verified EPDs.
- NCC 2025, Green Star, NABERS alignment.
- GHG Protocol + ISO 14064-1:2018 methodology.

Any new numeric/compliance claim must be approved by the owner before shipping.

## Owner

Steven Jenkins · steven@carbonconstruct.net
