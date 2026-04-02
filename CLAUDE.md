# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static website for **Seymour Speakers**, a Vancouver-based morning Toastmasters club. Hosted on GitHub Pages at `seymourspeakers.ca` (custom domain via CNAME file).

## Architecture

- **Pure static HTML site** — no build step, no bundler, no framework
- Three pages: `index.html` (home), `first-meeting.html` (visitor info/FAQs), `roles.html` (meeting role descriptions)
- **Tailwind CSS via CDN** (`cdn.tailwindcss.com`) with inline config in each page's `<script>` block — no separate config file
- Shared Tailwind theme (custom colors, fonts) is duplicated in each HTML file's `<script>` block
- **Fonts**: DM Sans (body) and Playfair Display (headings) via Google Fonts
- **No shared CSS/JS files** — all styles and scripts are inline within each HTML page
- Scroll-triggered animations use an IntersectionObserver pattern (`.reveal` class)
- `scraped/` directory contains the original site pages (reference only, not served)

## Development

Preview locally:
```
python3 -m http.server 8080
```
Then open `http://localhost:8080/index.html`

Deploy: push to `main` branch (GitHub Pages auto-deploys from root).

## Design System

Custom color tokens (defined in each page's Tailwind config):
- `ss-blue: #15273b` — primary navy
- `ss-dark-blue: #0b1c2b` — darker navy
- `ss-gold: #eec15c` — accent gold
- `ss-gold-dark: #d6ad4f` — darker gold
- `ss-cream: #faf8f3` — light background

## Important

This is a **public GitHub repository** deployed directly to GitHub Pages. Never commit sensitive information (API keys, personal data, credentials, internal URLs, etc.) — anything pushed to `main` is immediately public.

## Key Constraints

- When editing shared elements (nav, footer, Tailwind config), changes must be replicated across all three HTML files
- No build pipeline exists — all code must work directly in the browser via CDN
- Images live in `images/` and are referenced with relative paths
