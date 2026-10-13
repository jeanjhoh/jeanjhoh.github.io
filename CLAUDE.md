# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
# Preview site locally (live reload)
quarto preview

# Build site to _site/
quarto render

# Render a single file
quarto render index.qmd
```

## Architecture

This is a [Quarto](https://quarto.org) website for jeanoh.org.

- **`_quarto.yml`** — site config: title, theme (cosmo, heavily overridden), CSS, header/footer includes
- **`index.qmd`** — the single-page site. Raw HTML for the top bar, intro, and footer; Markdown `##` headings for sections
- **`styles.css`** — all visual styling; design tokens (colors, fonts, widths) live in `:root` at the top
- **`head.html`** — Google Fonts link (Newsreader for headings, Source Sans 3 for body)
- **`nav-active.html`** — small script: highlights the current section in the top nav, opens `.paper-link` links in a new tab
- **`photo.jpg`** — web-sized profile photo used by the page (`photo.png` is the full-resolution original, not referenced)
- **`_site/`** — build output (do not edit directly)

Layout model: each `## Heading {#id}` becomes a `section.level2`, styled as a two-column row (sticky heading on the left, content on the right). Section content must be wrapped in a `::: sec-body` fenced div so it occupies the right column as one block. Add a nav link in the top bar for any new section.

Do not use an `<h1>` in `index.qmd`; Quarto hoists the first `h1` out as the page title. The intro name uses a `div.name` with `role="heading"`.
