# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a **Hugo static site** for Federico Dallo's personal academic website, built with the [Wowchemy/starter-hugo-academic](https://wowchemy.com/docs/) theme. It is deployed automatically to Netlify on push to `main`.

- Live site: `https://federicodallo.netlify.app`
- Hugo version: `0.100.1` (pinned in `netlify.toml`)
- Theme: `starter-hugo-academic` (loaded as a Hugo module from `github.com/wowchemy/wowchemy-hugo-modules`)

## Commands

```bash
# Serve locally with live reload
hugo server

# Build the site to /public
hugo

# Build including future-dated content (used in Netlify branch/preview deploys)
hugo -F
```

There are no tests, linters, or build scripts beyond Hugo itself.

## Architecture

### Content model

All editable content lives under `content/`. The site is a single-page layout driven by **widgets** in `content/home/`, each backed by a Markdown file with YAML front matter. Key front-matter fields per widget:

- `active: true/false` — toggles the widget on/off without deleting it
- `weight` — controls vertical ordering on the homepage
- `widget` — the Wowchemy widget type (e.g. `about`, `experience`, `contact`)

### Author profile

The main profile is at `content/authors/admin/_index.md`. This YAML file controls the bio, education, interests, social links, and role shown in the `about` widget. The profile photo must be named `avatar.jpg` (or `avatar.png`) inside the same directory — the current files are `federico.png` / `federico400.jpg` (rename if the avatar is not displaying).

### Publications & other content types

Structured content (publications, posts, projects, events) lives in corresponding subdirectories under `content/`. Each item is a directory with an `index.md` file. The `publication/example/` and `publication/blogdown/` entries are starter examples.

### Navigation

`config/_default/menus.yaml` controls the top navbar. Commented-out entries (Posts, Projects, Talks, Publications) can be re-enabled by uncommenting.

### Static assets

- `static/uploads/` — files served at `/uploads/` (e.g. `resume.pdf`)
- `assets/media/` — images processed by Hugo's image pipeline

### Deployment

Netlify reads `netlify.toml`. The `production` context sets `HUGO_ENV=production`; branch and preview deploys pass `-F` and set `$DEPLOY_PRIME_URL` as the base URL. The `public/` directory is the build output (committed but not the source of truth — Hugo regenerates it).
