# Subagents

Subagents Claude Code should spawn when working in this repo. The repo is small (3 HTML files, ~55 KB total), so subagents should be used sparingly — prefer direct tool calls for single-file edits.

## Recommended

| Subagent | Trigger |
|---|---|
| `Plan` | Before adding a new SEO route. A new route touches `public/<slug>.html` + `public/sitemap.xml` + `public/robots.txt` (if disallowed) + `vercel.json` (if custom headers) — plan the set together so nothing drifts. |
| `Explore` | When searching for a shared pattern across all three pages (e.g., "which pages declare `og:image`?" or "find every `application/ld+json` block"). One agent, `quick` thoroughness. |
| `general-purpose` | Multi-step refactors touching all three HTML files at once — e.g., changing the shared hero layout, or migrating a meta-tag convention. |
| `claude-code-guide` | Questions about Claude Code features themselves (hooks, skills, MCP, settings) — keep these out of the main context. |

## Not relevant here

- `statusline-setup` — user-level setting, unrelated to the repo.
- Any worktree-isolated agent run — this repo has no long-running build to isolate.

## Invocation notes

- **One agent is almost always enough.** Parallel agents are overkill for a 3-file static site.
- Prefer `Explore` with `quick` thoroughness over `very thorough` — the codebase fits in one grep.
- Always brief the agent with the stack constraints from `CLAUDE.md` (no frameworks, inline CSS, no JS) so it doesn't propose framework-y solutions.
- Never let a subagent weaken the security headers in `vercel.json` or alter audit-grounded claims in copy.
