# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is Deng Pan's academic personal website, built with Jekyll and the Academic Pages template. It showcases publications, talks, teaching, and CV. The site deploys to GitHub Pages.

## Commands

```bash
# Install Ruby dependencies
bundle install

# Local development server (auto-reloads on .md/.html changes)
bundle exec jekyll serve -l -H localhost

# Build JavaScript assets
npm run build:js

# Docker development
docker compose up
```

**Important**: Changes to `_config.yml` require restarting the Jekyll server — it is NOT auto-reloaded.

## Architecture

- **`_config.yml`** — Site-wide settings (author info, collections, plugins). Must restart server on changes.
- **`_pages/`** — Static pages (about, CV, etc.)
- **`_publications/`**, **`_talks/`**, **`_teaching/`**, **`_portfolio/`** — Jekyll collections, each with individual `.md` files
- **`_layouts/`** — Page templates (single, talk, cv-layout, etc.)
- **`_includes/`** — Reusable components (author-profile, sidebar, seo.html, etc.)
- **`_sass/`** — SCSS stylesheets
- **`assets/`** — JS, CSS, images; `assets/js/_main.js` is the entry point
- **`markdown_generator/`** — Python scripts to generate publication/talk markdown from TSV

## Content Format

Publications and talks are markdown files with YAML frontmatter. Key fields vary by type but always include `layout` (references a layout) and `author_profile`.

## GitHub Pages Deployment

The `master` branch deploys to `pd90506.github.io`. `_site/` is the generated output — do not edit directly.
