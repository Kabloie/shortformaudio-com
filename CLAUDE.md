# CLAUDE.md — shortformaudio-com (shortformaudio.com)

## How we work

Antonio owns architecture, data, and product taste. Agents own execution.

**Do autonomously**
- Copy, layout, and content changes to the page
- Verify your own work before saying you're done: open the page and include a screenshot

**Stop and ask Antonio before**
- Pushing to `main` — it publishes the live site
- Changing the domain (`CNAME`)
- Adding analytics, scripts, or third-party embeds

**When you finish**
- Summarize in 5 bullets or fewer: what changed, how you verified it, what's risky
- Small changes, on a branch, never straight to `main`

## This repo

- A single static page, `index.html`, served at shortformaudio.com — a definition
  page for "short form audio". Assets in `audio/` and `images/`.
- **This repo is public.** Never commit secrets, internal notes, or anything about
  Kabloie that isn't already public.
- No build step. Verify by opening `index.html` in a browser at phone and desktop widths.

## The Kabloie repos

| Repo | What |
|---|---|
| kabloie-xyz | FastAPI backend, the API behind the app |
| kabloie-ios | The iOS app (UIKit/Swift) |
| kabloie-com | kabloie.com — Next.js web feed |
| kabloie-internal | Admin upload tool |
| kabloie-data | Scraping/ingest scripts |
| **shortformaudio-com** (this) | Static one-page site, public repo |
