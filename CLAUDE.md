# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Repo Is

This is **ndbailey.com**, the personal site of Nicholas Bailey. It is a static site
built with **Zensical** (a MkDocs-based system), configured via `zensical.toml`.
Content lives in `docs/` as Markdown files. Pushing to `main` triggers a GitHub
Actions workflow (`.github/workflows/docs.yml`) that runs `zensical build --clean`
and deploys to GitHub Pages. The custom domain `ndbailey.com` is set via
`docs/CNAME` and the `site_url` in `zensical.toml`.

## Common Commands

```bash
# Install dependencies (Python venv at .venv/)
pip install zensical

# Serve locally with live reload
zensical serve

# Build the static site
zensical build --clean
```

## Layout

This is a **topbar-only** site — both the left (primary) and right (secondary/TOC)
sidebars are hidden via CSS in `docs/assets/stylesheets/extra.css`. Top-level nav
items render as tabs in the header (`navigation.tabs` feature). Keep the nav flat:
each entry in the `nav` list in `zensical.toml` is one page = one tab.

## Content Structure

All content is in `docs/`. The nav is **explicitly defined** in `zensical.toml` —
adding a new `.md` file does **not** automatically add it to the site; it must be
listed under `nav`.

- `docs/index.md` — homepage. Uses the `home.html` template (`overrides/home.html`)
  for the minimal hero; hides navigation and toc via frontmatter.
- `docs/about.md`, `docs/projects.md`, `docs/repositories.md` — flat content pages,
  one per top-bar tab.
- `docs/assets/stylesheets/extra.css` — site-wide custom CSS and the brand palette.
- `docs/assets/favicon.svg` — favicon / header logo.

## Branding

The color palette is defined as `--brand-*` CSS variables at the top of
`extra.css`, then mapped onto Material's `--md-*` variables per color scheme
(`default` = light, `slate` = dark):

- `--brand-ocean` `#3c91e6` — primary / links
- `--brand-bloom` `#e951cf` — accent / highlight
- `--brand-sun` `#f5c842` — secondary accent
- `--brand-ghost` `#f2f1f9` — light background
- `--brand-ink` `#08060e` — text / dark background

## Adding Pages

1. Create a `.md` file in `docs/`.
2. Add it to the `nav` list in `zensical.toml` — otherwise it will not appear.
3. Images go in `docs/assets/`; reference with relative paths.

## Brand & Voice (for all site copy)

The site sells one positioning: **a practitioner who finds industrial energy savings,
proves the numbers survive scrutiny, and makes them legible to non-experts.** The PhD
is credibility backing, not the headline. Audience: industrial-energy and consulting
employers/clients, with secondary fit for national-lab / DOE-adjacent roles.

- **Essence (one line):** "I find energy savings on the plant floor, prove the numbers
  hold up, and write them so the people who sign off can act."
- **Hero tagline:** "Industrial energy savings, measured and defended."
- **Three pillars (the "How I work" cards):** Walk the floor · Defend the number ·
  Make it legible.
- **Differentiators to lean on:** the rare combination of field assessment +
  rigorous analysis + clear communication; audit-minded validation; teaching-grounded
  translation for plant managers.
- **Traps to avoid:** generic "I do energy assessments" (undifferentiated); leading
  with credentials instead of outcomes; reading as a researcher who dabbles, or as
  undirected across academia/consulting/labs. Frame breadth as **range within one lane**
  (energy-systems analysis + communication + shippable deliverables).

**Voice:** precise, plainspoken, evidence-led, quietly confident. Smart-casual academic.
Lead with the verb and the outcome; let numbers carry the claim; no corporate buzzwords,
no breathless hype.

### Hard copy constraints (do not violate)

- **No em-dashes anywhere.** Use commas, parentheses, colons, sentence breaks, or a
  middle dot (`·`) as a separator instead.
- **No email on the site.** Contact is LinkedIn (`in/ndbailey`) and GitHub only. Do not
  add a `mailto:` link or an email social entry.
- **Never fabricate** facts, names, numbers, or outcomes. Facility-level savings are
  client-confidential and not in the CV, so use clearly labeled placeholders like
  `[projected kWh per year]`, `[estimated $ per year]`, `[simple payback]`,
  `[facility type]`. Real, citable figures already in copy: PV degradation study
  ($1.8M annual value at risk; 1,091 MW; 91,290 installs) and Sikorsky supply-chain
  work (over $500K projected annual savings).
- **LinkedIn handle is `in/ndbailey`** (not `nicholas-bailey`).

## Zensical authoring reference (used by current pages)

- **Grids / cards** require both `attr_list` and `md_in_html` extensions (now enabled in
  `zensical.toml`). Card grid syntax:
  ```html
  <div class="grid cards" markdown>

  -   :material-icon:{ .lg .middle } __Title__

      ---

      Body text.

  </div>
  ```
- **Admonitions:** only **`info`** (blue) and **`abstract`** (pink) are used site-wide.
  These are the only two types themed in `extra.css`; do not introduce note/tip/warning/
  example/etc. Syntax `!!! info "Title"` or collapsible `??? abstract`.
- **Visual conventions:** the navbar/tabs are intentionally monochrome (no blue/pink in
  the active tab or underline). The hero text and the favicon/logo use a pink→yellow
  gradient (`--brand-bloom` to `--brand-sun`). Material/emoji icons (`:material-...:`)
  are **not** enabled, so don't use them in card titles or copy.
- **Card grids:** add the `two-up` class (`<div class="grid cards two-up" markdown>`) to
  force a two-column layout that collapses to one column on narrow screens.
- **Frontmatter keys:** `title`, `description` (HTML meta), `hide: [navigation, toc]`,
  `template`, `icon`, `status`. Content pages use `hide: [toc]`; the home page uses
  `template: home.html` plus `hide: [navigation, toc]`.
