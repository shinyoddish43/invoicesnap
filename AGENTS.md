# InvoiceSnap

A free invoice generator in one static page (`index.html`): fill in an invoice, download it as PDF, nothing uploaded, no sign-up. A "Pro" tier ($9) unlocks extras such as a custom colour. Drafts are kept in the browser's localStorage (`snap`). Private repo shinyoddish43/invoicesnap; not deployed anywhere yet.

**Coordination:** follow `~/.claude/templates/AGENT-COORDINATION.md` (repo log `.agents/activity.log`).

## Commands
```sh
python3 -m http.server 8000     # local preview: http://localhost:8000 (or a .claude/launch.json entry for the browser pane)
```
No build step and no tests yet: check changes in the browser at phone and desktop widths (skill `web-design-review`).

## Rules
1. Everything stays in the visitor's browser: no uploads, no analytics or trackers.
2. Keep it one self-contained file unless the owner decides otherwise.

## Things that are easy to get wrong
- The Pro unlock is client-side only: `PRO_KEY` sits in the page source, so anyone can read it or flip `PRO`. Real payments need server-side verification (`site-audit security`).
- Launch placeholders still in the page: `PAY_LINK` is empty and the canonical URL is `https://YOUR-SITE/`.

## Status
- Prototype from 2026-09-30. Before launch: a real payment link and server-checked unlock, the page's URL, and `/site-audit launch`.
