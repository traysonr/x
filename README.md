# Engineering Fieldnotes

A theme-free Hugo portfolio for project listings and chronological engineering logs. Markdown and images live in `content/`; templates live in `layouts/`; styling lives in `assets/css/main.css`.

## Preview locally

Install Hugo Extended, then from this folder run:

```sh
hugo server
```

Open the local URL Hugo prints, usually `http://localhost:1313/engineering-portfolio/`. To create a production build locally, run `hugo --gc --minify`.

## Add a project

Create `content/projects/my-project/_index.md` with front matter like:

```yaml
---
title: "My project"
description: "A short description shown on the project list and project page."
date: 2026-06-01
tags: ["CAD", "Embedded"]
thumbnail: "thumbnail.jpg"
hero: "hero.jpg"
---
Introductory Markdown for the project page.
```

Put its thumbnail and optional hero beside `_index.md`. Add update files under `updates/`, each with a `title` and timestamped `date` in front matter, followed by ordinary Markdown. Put update-specific images in the same update folder and link them with relative Markdown paths. Hugo displays updates oldest first.

Markdown images, tables, links, and fenced code are supported. Use Hugo?s `{{< youtube VIDEO_ID >}}` shortcode to embed a YouTube video in an update.

## GitHub Pages

This repository is deployed at `https://traysonr.github.io/engineering-portfolio/`. The workflow builds Hugo on each push to `main` and publishes the output to the `gh-pages` branch. GitHub Pages serves that branch. If you fork this project, update `baseURL` in `hugo.yaml` and the source link in the site footer.
