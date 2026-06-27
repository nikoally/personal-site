# ndbailey.com

Personal site of Nicholas Bailey — built with [Zensical](https://zensical.org)
(a MkDocs-based static site generator) and deployed to GitHub Pages.

## Develop

```bash
python -m venv .venv && source .venv/bin/activate
pip install zensical

zensical serve          # live-reload dev server
zensical build --clean  # build the static site into ./site
```

## Structure

- `docs/` — Markdown content (`index.md`, `about.md`, `projects.md`, `repositories.md`).
- `zensical.toml` — site config and navigation. The nav is explicit: a page only
  appears if it's listed under `nav`.
- `overrides/` — template overrides (`home.html` is the homepage hero).
- `docs/assets/stylesheets/extra.css` — custom styling and the brand palette.
- `docs/CNAME` — custom domain (`ndbailey.com`).

## Deploy

Pushing to `main` runs `.github/workflows/docs.yml`, which builds with Zensical
and publishes to GitHub Pages.
