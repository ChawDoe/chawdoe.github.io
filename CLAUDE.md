# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static personal academic website for Deyu Zhou (AI researcher at HKUST-GZ). Deployed via GitHub Pages. No build system, no package manager, no framework — just plain HTML, CSS, and vanilla JavaScript.

## Structure

```
deyuzhou-ust.github.io-main/
├── index.html       # Single-page site (all markup, styles, and scripts)
├── stylesheet.css   # Legacy CSS file (Lato font-face declarations + base styles; main styles are inline in index.html)
└── images/          # Profile photo, publication figures, demo videos (.jpg, .png, .mp4)
```

## Development

No build or install step. Open `index.html` directly in a browser or serve with any static file server:

```bash
cd deyuzhou-ust.github.io-main
python3 -m http.server 8000
```

## Architecture Notes

- **All CSS is inline** in `index.html` inside a `<style>` tag using CSS custom properties (`:root` variables for `--primary`, `--accent`, etc.). `stylesheet.css` exists separately but only provides font-face declarations and legacy base styles.
- **Responsive layout** uses CSS Grid with a mobile breakpoint at 768px.
- **Modal viewer** (vanilla JS at bottom of `index.html`) handles click-to-expand for `<figure>` elements, cloning video nodes when needed. Supports Escape key and backdrop click to close.
- **SEO** meta tags, canonical URL, and semantic HTML are in place. Comments in the HTML are in Chinese.
- **No templating** — publication cards are hand-written HTML blocks. To add a new publication, duplicate an existing `.pub-card` div and update its content.
