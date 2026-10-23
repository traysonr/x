---
title: "How this portfolio is put together"
description: "A visual map of the Hugo pages, Markdown files, and reusable components behind this project log."
date: 2026-10-23
tags: ["Hugo", "Markdown", "GitHub Pages"]
cardLabel: "SITE GUIDE"
thumbnail: "guide-map.svg"
hero: "guide-map.svg"
layout: "guide"
---

This is the map I wish I had when I opened the repo. The content lives in Markdown bundles; Hugo turns those files into the home page and project logs; the shared templates and stylesheet control how everything reads.

## Page anatomy

The diagram maps visible page elements to the files that provide them. Text and project facts stay in content files. Templates arrange them, and CSS sets the visual system.

## The parts you will edit most

| Goal | Start here | What it controls |
| --- | --- | --- |
| Add or revise a project | `content/projects/<slug>/_index.md` | Title, short card description, tags, hero image, and project introduction |
| Add a dated build note | `content/projects/<slug>/updates/YYYY-MM-DD-short-title.md` | One chronological update, written in ordinary Markdown |
| Change card and page structure | `layouts/partials/project-card.html`, `layouts/projects/list.html` | Shared project card and project log layout |
| Change colors, type, spacing, and image sizing | `assets/css/main.css` | The site-wide visual style |
| Change site title and footer description | `hugo.yaml` and `layouts/_default/baseof.html` | Browser metadata and shared site chrome |

The project description is deliberately short: it appears on the home page and again below the title on the project page. Put the fuller context in the Markdown body. The `thumbnail` and `hero` fields point to files inside that project's bundle, so images stay next to the content they illustrate.

## Markdown that works in a build log

Use headings, paragraphs, lists, tables, fenced code blocks, and links where they help someone scan the update. For an image with a useful caption, use:

```text
{{</* figure src="plot.png" alt="Signal power over time" caption="A short note about what this plot shows." */>}}
```

For a public YouTube clip, use the privacy-enhanced embed shortcode:

```text
{{</* youtube id="VIDEO_ID" title="Bench test video" caption="What to look for in the clip." */>}}
```

Keep titles and summaries in sentence case. A dated note should say what changed, what you observed, and what the evidence supports. A plot should carry units and a plain caption; label estimates as estimates and don't turn a promising decode into a confirmed device identification.
