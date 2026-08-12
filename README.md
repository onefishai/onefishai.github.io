# Onefish AI — Public Site

Onefish AI's public site: tips, walkthroughs, and live examples of the automation tricks we use to cut busywork for the people we work with.

- Live site: https://onefishai.github.io
- Repo: https://github.com/onefishai/onefish.github.io

## Structure

```
index.html                    Homepage — hero, nav, featured tutorial card
assets/css/theme.css           Color tokens (light/dark via CSS vars)
assets/css/shared.css          Shared layout/component classes (.nav, .card, .btn, .footer, etc.)
assets/img/                    Images (currently empty)
tutorials/lookup-tables.html   First tutorial — also the template for new tutorial pages
sheets/                        Google Sheets embed pages
demos/                         Live demo embeds (future)
```

No build step, no framework — just static HTML/CSS served directly by GitHub Pages.

## How to add a tutorial

1. Copy `tutorials/lookup-tables.html` as a starting template — it demonstrates the `.article-header` block, article sections, an example table, and the back-link pattern.
2. Update `<title>`, the meta description, `.article-header__eyebrow` / `__title` / `__lede`, and the article body sections.
3. Only use existing classes from `assets/css/theme.css` and `assets/css/shared.css` — avoid hardcoded colors. Put page-specific layout in a `<style>` block in `<head>`, same as the existing pages.
4. Link the new tutorial from `index.html` (nav and/or a new `.card` in the Tutorials section).

## How to embed a Google Sheet

See `sheets/index.html` for the reference pattern: publish the sheet to the web from Google Sheets, then embed it via `<iframe>` with `?widget=true&headers=false`. Full instructions live on that page itself.

## GitHub Pages config notes

- Pages should be configured to serve from the `main` branch, root (`/`) directory — Settings > Pages in the GitHub repo.
- No build step or Jekyll processing needed. GitHub Pages runs Jekyll by default, which ignores files/folders starting with `_`. None of our filenames do today, but if that changes and something stops rendering, add a `.nojekyll` file at root to disable Jekyll.
- No custom domain configured yet. If one is added later, it goes in a `CNAME` file at root.

## Local preview

```bash
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.
