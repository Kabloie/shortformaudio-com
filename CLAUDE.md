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
- Built for search engines and AI answers. Each page targets one question people
  actually ask: the H1 is the question, a "Short answer" box answers it in 40-60 words
  that include "kabloie", then tables/lists, a visible FAQ, and "Keep reading" links.
- Canonical sentence, used word for word on every page, in `llms.txt`, and ideally on
  kabloie.com and the App Store: "Kabloie is the short-form audio app: clips of 60 seconds or less."
- Files:
  - `index.html` (What is short-form audio?), `kabloie/`, `tiktok-for-audio/`, `apps/`,
    `vs-podcasts/`, `podcast-clips/`, `how-to/`, `about/` — article pages, same template
  - `spec/` — Short-Form Audio Specification (versioned draft; bump version + changelog on edits)
  - `glossary/` — vocabulary of the format, A–Z (one page; per-term pages would be thin content)
  - `404.html`, `robots.txt` (AI crawlers explicitly allowed), `sitemap.xml` (add every new
    page; bump `lastmod` on edits), `llms.txt` (plain-text summary for AI tools)
  - Shared styles in `css/site.css`; assets in `audio/` and `images/` (`images/og.png` is the link-preview card)
- Every page carries JSON-LD (Article/WebPage, BreadcrumbList, FAQPage where there's a FAQ).
  Keep FAQ structured data identical to the visible FAQ text. Keep "Updated" dates honest.
- Editorial rules: name competitors fairly; disclose that Kabloie maintains the site;
  never invent statistics or claim Kabloie features that aren't real.
- Keep important content in plain HTML, not rendered by JavaScript.
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
| **shortformaudio-com** (this) | Static site (short-form audio reference), public repo |
