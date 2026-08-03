# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

Jonah Elkhouri's personal portfolio site: a Jekyll static site using the `minimal-mistakes-jekyll`
theme (dark skin), hosted on GitHub Pages at `https://jelkhouri.github.io`. There is no
application code, backend, or test suite — this is a content/config repo.

See `MAINTENANCE.md` for the full maintenance guide (outstanding content gaps, repo structure
table, and step-by-step instructions for adding posts/projects/pages). Read it before making
content changes — it documents conventions in more depth than this file does.

## Commands

```bash
bundle install          # first time, or after Gemfile changes
bundle exec jekyll serve   # local dev server at http://localhost:4000, live rebuild on save
bundle exec jekyll build   # production build to _site/ (what CI runs)
bundle update            # pick up Jekyll/theme/plugin updates
```

There is no lint or test command. Always run `bundle exec jekyll serve` locally and check the
affected page before pushing — a broken build fails silently in the GitHub Actions tab (Pages
just won't update) rather than erroring visibly.

## Deployment

Push to `main` → `.github/workflows/jekyll.yml` runs `bundle exec jekyll build` and deploys
`_site/` to GitHub Pages automatically. No manual deploy step exists. `_site/`, `.jekyll-cache/`,
and `vendor/` are gitignored build output — never hand-edit or commit them.

## Architecture

- **Two content models coexist**: `_posts/` is Jekyll's built-in `posts` collection (blog
  entries, dated filenames, listed at `/blog/`); `_projects/` is a custom collection defined in
  `_config.yml` (`output: true`, `permalink: /projects/:name/`) for project write-ups, looped
  over manually in `projects.md` via `site.projects | sort: "date" | reverse`. New posts need no
  registration; new projects likewise appear automatically once the file exists.
- **Front matter defaults are centralized in `_config.yml`** under `defaults:`, keyed by
  collection `type` (`posts`, `pages`, `projects`) — not set per-file. All three get
  `layout: single` and `author_profile: true`; posts additionally get `read_time: true` and
  `toc: true`. Don't repeat these in individual files' front matter.
- **Navigation is data-driven**: `_data/navigation.yml` defines the top nav bar. Adding a new
  top-level page (`pagename.md` at repo root) does **not** automatically add it to the nav — it
  must be added to `_data/navigation.yml` `main:` separately.
- **Top-level pages** (`about.md`, `resume.md`, `blog.md`, `projects.md`, `index.html`) are
  mostly thin front-matter shells; `index.html` uses `layout: home`, the others `layout: single`
  (inherited from defaults). `about.md` and `resume.md` currently have no body content.
