# Foret Lab

A basic landing site for the **Foret Lab** academic research group, built with
[Quarto](https://quarto.org) — the open-source scientific and technical
publishing framework for Markdown and R.

## Pages

| Page         | Source           | Description                          |
| ------------ | ---------------- | ------------------------------------ |
| Home         | `index.qmd`      | Landing page                         |
| About        | `about.qmd`      | About the lab, mission, and contact  |
| Projects     | `projects.qmd`   | Overview of research projects        |
| Members      | `members.qmd`    | Lab members and how to join          |

Site-wide configuration (title, navigation, theme) lives in `_quarto.yml`, and
custom styling is in `styles.css`.

## Prerequisites

- [Quarto CLI](https://quarto.org/docs/get-started/) (v1.4 or newer recommended)
- Optional: [R](https://www.r-project.org/) if you add executable R code chunks
  to any `.qmd` pages

Verify your install:

```bash
quarto --version
```

## Local development

Start a live-reloading preview server. This rebuilds the site and refreshes your
browser automatically as you edit:

```bash
quarto preview
```

By default the preview is served at <http://localhost:4200>. To pick a specific
port:

```bash
quarto preview --port 8080
```

## Production build

Render the full static site into the `_site/` directory (set in `_quarto.yml`):

```bash
quarto render
```

The contents of `_site/` are plain HTML/CSS/JS and can be deployed to any static
host (GitHub Pages, Netlify, Vercel, S3, etc.).

To preview the production build locally, serve the output directory with any
static file server, for example:

```bash
python3 -m http.server --directory _site 8000
```

## Project structure

```
.
├── _quarto.yml     # Site config: navigation, theme, output dir
├── index.qmd       # Home / landing page
├── about.qmd       # About page
├── projects.qmd    # Projects page
├── members.qmd     # Members page
├── styles.css      # Custom site styles
└── _site/          # Generated build output (git-ignored)
```

## Deployment

Quarto has built-in publishing commands. For example, to publish to GitHub
Pages:

```bash
quarto publish gh-pages
```

See the [Quarto publishing docs](https://quarto.org/docs/publishing/) for other
targets.
