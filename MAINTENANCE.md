# Site Maintenance Guide

Portfolio site for Jonah Elkhouri, built with [Jekyll](https://jekyllrb.com/) using the
`minimal-mistakes-jekyll` theme (dark skin), hosted on GitHub Pages at
`https://jelkhouri.github.io`. Deploys automatically via GitHub Actions on every push to `main`
(see `.github/workflows/jekyll.yml`) — there is no manual build/deploy step.

## 1. Outstanding action items (found while auditing the repo)

These are gaps in the current content that should be filled in:

- [ ] `about.md` — front matter only, no bio text written yet.
- [ ] `resume.md` — front matter only, empty. Decide on format: write resume content directly in
      Markdown, or embed/link a PDF (e.g. drop it in `assets/files/resume.pdf` and link to it).
- [ ] `_posts/2026-06-23-prediction-markets-project.md` — still has placeholder text
      ("Write about the project here...", "..."). Needs a real write-up.
- [ ] `_projects/kalshi-trends.md` — still has placeholder text ("Write your full project
      write-up here..."). Needs Methodology/Results filled in.
- [ ] `assets/images/` — currently empty. Add header images / chart screenshots referenced by
      posts and projects.
- [ ] `_config.yml` — `email: jonahelkhouri@email.com` looks like a typo (not a real domain);
      confirm whether it should be your actual email address.
- [ ] No favicon set — minimal-mistakes supports a `site.logo` / favicon via `_config.yml`; not
      currently configured.

## 2. Local development

```bash
bundle install          # first time / after Gemfile changes
bundle exec jekyll serve
```

Preview at `http://localhost:4000`. `_site/`, `.jekyll-cache/`, and `vendor/` are gitignored —
don't commit build output.

Always preview locally before pushing to `main` — a broken build will fail silently-ish in the
GitHub Actions tab (Pages won't update) rather than erroring in your face.

## 3. Repo structure

| Path | Purpose |
|---|---|
| `_config.yml` | Site title, author info, nav/plugin config, collections |
| `_data/navigation.yml` | Top nav bar links (About / Projects / Blog / Resume) |
| `about.md`, `resume.md`, `blog.md`, `projects.md`, `index.html` | Top-level pages |
| `_posts/` | Blog posts (Jekyll's built-in `posts` collection) |
| `_projects/` | Project write-ups (custom `projects` collection, output to `/projects/:name/`) |
| `assets/images/` | Images referenced from posts/projects |
| `.github/workflows/jekyll.yml` | CI: builds with `bundle exec jekyll build`, deploys to Pages |

## 4. Adding a new blog post

1. Create `_posts/YYYY-MM-DD-slug-title.md` (filename date is required by Jekyll).
2. Front matter template:
   ```yaml
   ---
   title: "Post Title"
   date: YYYY-MM-DD
   categories: [projects, data]   # adjust as needed
   tags: [python, ...]
   toc: true
   ---
   ```
3. Write content in Markdown below the front matter. Inline images:
   `![alt text](/assets/images/filename.png)`.
4. Posts show up automatically at `/blog/` (paginated, 5 per page per `_config.yml`) — no
   registration needed elsewhere.

## 5. Adding a new project

1. Create `_projects/project-slug.md`.
2. Front matter template:
   ```yaml
   ---
   title: "Project Title"
   date: YYYY-MM-DD
   excerpt: "One-sentence summary shown on the /projects/ listing."
   tags: [python, ...]
   ---
   ```
3. Body: at minimum an Overview / Methodology / Results structure (see `kalshi-trends.md` for
   the existing skeleton).
4. `projects.md` loops over `site.projects` sorted by date automatically — no registration
   needed elsewhere.

## 6. Adding a new top-level page

1. Create `pagename.md` at repo root with front matter (`title`, `permalink`).
2. Add an entry to `_data/navigation.yml` under `main:` so it shows up in the nav bar — pages
   are **not** auto-added to nav.

## 7. Updating the resume

Since `resume.md` is currently empty, decide once and document the choice here:
- **Markdown-in-page** — easiest to keep in sync with the site's styling, but means retyping
  changes instead of just re-exporting a PDF.
- **PDF embed/link** — put the PDF under `assets/files/`, link/embed it from `resume.md`; faster
  to update by just swapping the file, but styling won't match the site theme.

Whichever you pick, review/update at least once per semester or after any internship, project,
or award worth adding.

## 8. Routine maintenance checklist

- After finishing a project: write it up in `_projects/`, optionally cross-post a narrative
  version to `_posts/`, add supporting images to `assets/images/`.
- Periodically run `bundle update` to pick up Jekyll/theme/plugin security and bug fixes, then
  `bundle exec jekyll serve` locally to confirm nothing broke before pushing.
- Check for broken links/images occasionally, especially after renaming files (permalinks are
  derived from filenames and `_config.yml`'s `permalink:` setting).
- Keep `_config.yml`'s `description`, `author.bio`, and social links current as your focus areas
  change.

## 9. Git workflow reminder

Changes aren't published until you commit and push — nothing here happens automatically:

```bash
git add <files>
git commit -m "..."
git push origin main   # triggers the GitHub Actions build + deploy
```
