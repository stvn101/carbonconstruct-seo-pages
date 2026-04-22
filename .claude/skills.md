# Skills

Skills that pair well with this repo. Invoke via `/<skill-name>` in Claude Code.

## Recommended

| Skill | When to use it here |
|---|---|
| `/review` | Before pushing any HTML/meta changes to `main`. Catches broken schema.org JSON-LD, stale canonical URLs, and sitemap drift. |
| `/security-review` | Whenever `vercel.json` headers change, or when adding an external resource (new font host, external image, third-party script). |
| `/simplify` | After hand-editing HTML — dedupes inline CSS and repeated markup across the three landing pages. |
| `/update-config` | If adding a SessionStart hook (e.g., to verify `public/sitemap.xml` entries match files on disk) or allowlist dev/serve commands to cut permission prompts. |
| `/fewer-permission-prompts` | After a handful of sessions, to allowlist the read-only commands (`ls`, `cat public/*.html`, `curl -I https://carbonconstruct.online`) that get prompted repeatedly. |

## Not relevant here

- `/claude-api` — this repo has no Anthropic SDK code.
- `/session-start-hook` — only needed if setting up Claude Code on the web for this repo.
- `/init` — CLAUDE.md already exists at repo root.
- `/keybindings-help` — user-level, unrelated to the repo.
- `/loop` — no recurring tasks tied to this repo.

## Invocation notes

- Skills are user-triggered in the interactive CLI; Claude cannot call them autonomously for you.
- `/review` and `/security-review` run against the pending diff on the current branch — stage or commit work first.
