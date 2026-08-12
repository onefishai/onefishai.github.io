# Onefish AI — Org Homepage

Onefish AI's public homepage: tips, walkthroughs, and live examples of the automation tricks we use to cut busywork for the people we work with.

- Live site: https://onefishai.github.io
- Repo: https://github.com/onefishai/onefishai.github.io

## Structure

```
index.html                    Homepage — hero, nav, featured tutorial card
assets/css/theme.css           Color tokens (light/dark via CSS vars)
assets/css/shared.css          Shared layout/component classes (.nav, .card, .btn, .footer, etc.)
assets/img/                    Images (currently empty)
```

No build step, no framework — just static HTML/CSS served directly by GitHub Pages.

This repo is now just the homepage shell. Tutorials, Google Sheet embeds, and demos live in the sibling
[`onefishai/tutorials`](https://github.com/onefishai/tutorials) repo, served at
[onefishai.github.io/tutorials/](https://onefishai.github.io/tutorials/) via GitHub Pages project-site routing.
See that repo's own README for how to add a tutorial or embed a Google Sheet.

## GitHub Pages config notes

- Pages should be configured to serve from the `main` branch, root (`/`) directory — Settings > Pages in the GitHub repo.
- No build step or Jekyll processing needed. GitHub Pages runs Jekyll by default, which ignores files/folders starting with `_`. None of our filenames do today, but if that changes and something stops rendering, add a `.nojekyll` file at root to disable Jekyll.
- No custom domain configured yet. If one is added later, it goes in a `CNAME` file at root.

## Local preview

```bash
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.
