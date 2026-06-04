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
host.

To preview the production build locally, serve the output directory with any
static file server, for example:

```bash
python3 -m http.server --directory _site 8000
```

## Project structure

```text
.
├── _quarto.yml     # Site config: navigation, theme, output dir
├── index.qmd       # Home / landing page
├── about.qmd       # About page
├── projects.qmd    # Projects page
├── members.qmd     # Members page
├── styles.css      # Custom site styles
└── _site/          # Generated build output (git-ignored)
```

## Continuous integration

Every push and pull request runs the [`CI`](.github/workflows/ci.yml) workflow,
which has two jobs:

- **Lint Markdown** — runs `markdownlint-cli2` over all `.md` and `.qmd`
  sources (configured in `.markdownlint-cli2.yaml`).
- **Build site** — installs Quarto and runs `quarto render`, so any
  misconfiguration or render error fails the build.

To reproduce the lint step locally:

```bash
npx markdownlint-cli2 "**/*.md" "**/*.qmd"
```

## Deployment

`quarto render` produces a self-contained static site in `_site/`. Because the
output is plain HTML/CSS/JS, it can be deployed with whatever method suits your
workflow — copy the directory to a web server, sync it to object storage, serve
it from a CDN, or use Quarto's built-in `quarto publish` command.

See the [Quarto publishing docs](https://quarto.org/docs/publishing/) for the
available publishing targets.
