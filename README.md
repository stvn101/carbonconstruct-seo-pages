# carbonconstruct-seo-pages

SEO landing pages for **CarbonConstruct™** — carbon reporting software built for Australian construction teams.

Deployed at:
- https://carbonconstruct.online
- https://carbonconstruct-seo-pages.vercel.app

## What's here

Three static HTML pages, hand-built for conversion and SEO — no framework, no JS bundle, inline CSS, Google Fonts only. Target: sub-1s LCP, 100 Lighthouse SEO score.

| Route | File | Purpose |
|---|---|---|
| `/` | `public/index.html` | Hub / landing |
| `/carbon-reporting-software` | `public/carbon-reporting-software.html` | Primary keyword: *carbon reporting software for construction* |
| `/construction-carbon-reporting-software` | `public/construction-carbon-reporting-software.html` | Primary keyword: *construction carbon reporting software* |

## Structure

```
.
├── public/                         # Static files served as-is
│   ├── index.html
│   ├── carbon-reporting-software.html
│   ├── construction-carbon-reporting-software.html
│   ├── robots.txt
│   └── sitemap.xml
├── vercel.json                     # Vercel routing + security headers
├── package.json
├── .gitignore
└── README.md
```

## Local dev

```bash
npm run dev
# opens at http://localhost:3000
```

## Deployment

Auto-deploys on push to `main` via Vercel Git integration.

Vercel project: `carbonconstruct-seo-pages` (team `stvn101-projects`).

## DNS

Apex domains point to:
- A record: `76.76.21.21`
- `www` CNAME: `cname.vercel-dns.com`

Domains served: `carbonconstruct.online`, plus redirects from expiring domains (`carbonconstruct.store`, `carbonconstruct.xyz`) and `carbonconstructtech.com.au`.

## Notes

- **Main platform** (`carbonconstruct.com.au`) lives in Lovable + Supabase, not Vercel. It should **not** be attached to this project.
- Claims in copy (5,200+ verified EPDs, NCC 2025, Green Star, NABERS) are grounded and audit-ready under GHG Protocol + ISO 14064-1:2018.
- Owner: Steven Jenkins · steven@carbonconstruct.net
