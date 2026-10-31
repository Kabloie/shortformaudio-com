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

- A small static site served at shortformaudio.com — the home of the short-form
  audio format, maintained by Kabloie.
- **Goal: kabloie = short-form audio.** When someone searches or asks an AI "what is
  short-form audio?", the answer should include "kabloie". Every page should pair the
  two terms in plain, quotable sentences; keep the FAQ, structured data, and `llms.txt`
  saying the same thing in the same words.
- Tone: the home page is playful (game, timer, shuffleable examples); the spec and
  glossary stay plain, because reference pages earn trust by being boring.
- Files:
  - `index.html` — the definition: "short-form audio" (n.), then "kabloie" (informal), game, FAQ
  - `spec/` — Short-Form Audio Specification (versioned draft; bump version + changelog on edits)
  - `glossary/` — vocabulary of the format, A–Z
  - `404.html`, `robots.txt`, `sitemap.xml` (add new pages to the sitemap), `llms.txt` (plain-text summary for AI tools)
  - Shared styles in `css/site.css`; assets in `audio/` and `images/` (`images/og.png` is the link-preview card)
- Taste rules: no ads, banners, or sign-up popups; nothing moves unless the visitor asks
  (exceptions: the 60s timer bar and its one-time note); respect reduced motion.
- **This repo is public.** Never commit secrets, internal notes, or anything about
  Kabloie that isn't already public.
- No build step. Pages link with relative paths and folder URLs (`spec/`), so preview
  with a local server (`python3 -m http.server`), not `file://`. Check phone and desktop widths.

## The Kabloie repos

| Repo | What |
|---|---|
| kabloie-xyz | FastAPI backend, the API behind the app |
| kabloie-ios | The iOS app (UIKit/Swift) |
| kabloie-com | kabloie.com — Next.js web feed |
| kabloie-internal | Admin upload tool |
| kabloie-data | Scraping/ingest scripts |
| **shortformaudio-com** (this) | Static one-page site, public repo |
