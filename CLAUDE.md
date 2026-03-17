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

- **`_quarto.yml`** — site config: title, navbar, theme (cosmo + brand), global CSS
- **`*.qmd`** — page sources in Quarto Markdown (YAML frontmatter + Markdown + optional R/Python)
- **`styles.css`** — custom CSS layered on top of the cosmo Bootstrap theme
- **`_site/`** — build output (do not edit directly)

The `brand` theme entry in `_quarto.yml` expects a `_brand.yml` file for brand tokens (colors, fonts). If one doesn't exist yet, Quarto will fall back to cosmo defaults.

New pages are added by creating a `.qmd` file and registering it under `website.navbar` (or `website.sidebar`) in `_quarto.yml`.
