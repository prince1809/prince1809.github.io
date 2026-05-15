# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a static personal resume/portfolio site hosted on GitHub Pages at `resume.princekr.com`. There is no build step, bundler, or package manager — it is plain HTML, CSS, and fonts served directly by GitHub Pages.

## Structure

- `index.html` — the main resume page (HTML with microformats: hResume, hCard, hCalendar)
- `css/resume.css` — all custom styles; uses rem-based sizing with responsive breakpoints for phone (≤480px), tablet (768px), and desktop (992px+)
- `css/bootstrap.min.css` — Bootstrap (vendored, do not modify)
- `fonts/` — vendored icomoon icon font (custom icons: `icon-sslc`, `icon-be`, `icon-hslc`) and Bootstrap glyphicons
- `CNAME` — custom domain config (`resume.princekr.com`)

## Development

No build or install step. Open `index.html` directly in a browser, or use any static file server:

```bash
python3 -m http.server 8000
```

Changes are deployed by pushing to the `master` branch; GitHub Pages serves the result automatically.

## Key conventions

- The HTML uses microformat classes (`hresume`, `vcard`, `fn`, `adr`, `dtstart`, etc.) for semantic markup — preserve these when editing content.
- Skill proficiency is encoded via `data-rating` attributes (1–6) on `.skill` elements; CSS uses `clip` to render circular progress indicators.
- The `.highlights` skill list renders circular SVG-like indicators; the `.normal` list renders text badges sized by `data-rating`.
- Responsive layout is Bootstrap grid (`col-xs-*`, `col-md-*`, `col-lg-*`).
