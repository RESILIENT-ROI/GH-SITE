# CLAUDE.md

1. This file is written for Claude. It describes this repository and how Claude should behave here.
2. Make sure user scope claude.md is also read and obeyed `%USERPROFILE%\.claude\CLAUDE.md`
   1. pay special attention to Conversation protocol, in there

## What This Repo Is

**RESILIENT-ROI/GH-SITE** — Hugo + PaperMod site, scaffolded from `DBJARH/DBJ_ICEBERG`.

- Repo: https://github.com/RESILIENT-ROI/GH-SITE
- Deployed via GitHub Actions on push to `main`

## Your Role Here

Content editor and Hugo technician:
- Adding or editing posts
- Fixing Hugo/PaperMod configuration
- Managing the deploy workflow

## Hugo Conventions

- **Theme:** PaperMod, installed as a git submodule at `themes/PaperMod`
- **Config:** `hugo.toml` in root
- **Content:** `content/posts/` — one folder per post
- **Page bundles:** every post is `content/posts/post-name/index.md` with images local to that folder
- **Search page:** `content/search.md` — do not remove, PaperMod requires it
- **Build:** `hugo --minify` — always use Extended variant (required for PaperMod SCSS)
- **Local verification:** before calling any layout/CSS/template change done, run `hugo server --minify` and check it at `http://localhost:1313/`. Never claim a visual change works without having checked it against the dev server first.

## Post Front matter

Every post must have at least these fields:

```yaml
---
title: "Post Title"
date: YYYY-MM-DD
description: "One sentence — used in post listings and SEO."
tags: ["tag1", "tag2"]
author: "Dusan B. Jovanovic"
---
```

Optional cover image (local to post folder):

```yaml
cover:
  image: "filename.jpg"
```

## Still To Do (scaffold leftovers)

- `baseURL` in `hugo.toml` is the GitHub Pages default. Set a custom domain and add `static/CNAME` if wanted.
- `static/favicon/` is empty — add favicons, then uncomment the block in `layouts/_partials/extend_head.html`.
- Comments are off. To enable Giscus: set `comments = true`, fill the `[params.giscus]` block in `hugo.toml`, and replace `TODO_REPO_ID` / `TODO_CATEGORY_ID` in `layouts/_partials/comments.html`.
- `params.description` and `homeInfoParams` are empty.

## Behavioral Rules

1. **No padding.** No summaries, no affirmations.
2. **Do not invent URLs.**

## Document versioning

- Every markdown file **SHOULD** (not must) carry a decimal `version:` key in its front matter:

```yaml
---
version: 0.1
---
```

- `0.1` .. `1.0` — pre-releases leading up to release 1
- `1.1` .. `2.0` — releases 1.1 through 2.0

SHOULD, not MUST: where front matter already exists just add the `version` key without disturbing the rest.
