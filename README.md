# dinogen.github.io

Personal publishing system for sharing practical lessons from software
engineering, AI, data, banking software, legacy systems, architecture, and
programming.

The project is built around a simple principle: write the insight once, keep
the original article as the source of truth, and adapt it for the website and
social platforms only after human review.

## Status

The website is a Jekyll site deployed by GitHub Actions to GitHub Pages.
`contents/` remains the canonical source for articles. Social publishing,
search, analytics, and content transformation are still future work.

## Editorial Workflow

```text
idea -> draft -> review -> canonical article -> platform adaptations
      -> human approval -> publication
```

AI may help edit and adapt an article, but it must preserve the author's
original insight. Nothing should be published automatically without human
approval.

## Repository Layout

| Directory | Purpose |
| --- | --- |
| [`contents/`](contents/) | Canonical article Markdown and the long-term knowledge base |
| [`ideas/`](ideas/) | Low-friction inbox for observations and rough ideas |
| [`generated/`](generated/) | Platform-specific drafts for LinkedIn, X, and Instagram |
| [`images/`](images/) | Visual assets and future reusable templates |
| [`scripts/`](scripts/) | Future validation, transformation, and publishing automation |
| [`ai-friendly-docs/`](ai-friendly-docs/) | Focused documentation for contributors and agents |

The complete publishing guide is in
[`ai-friendly-docs/jekyll-manual.md`](ai-friendly-docs/jekyll-manual.md).

The project roadmap and proposed architecture are documented in
[`system_description.md`](system_description.md).

## Content Principles

- Treat `contents/` as the source of truth.
- Adapt the same idea for each platform instead of independently inventing
  multiple versions.
- Keep company-sensitive and confidential information out of all content.
- Review technical accuracy, tone, readability, links, and originality before
  publication.
- Prefer a sustainable rhythm of approximately three publications per week.

## Planned Direction

The longer-term system is intended to provide:

- A lightweight website generated from Markdown.
- Search, topics, RSS, and related articles.
- AI-assisted drafts for LinkedIn, X, and Instagram.
- Human-in-the-loop quality and confidentiality checks.
- GitHub-based website deployment.
- A publishing calendar and analytics for learning which ideas matter.

The repository includes a GitHub Pages workflow in
[`.github/workflows/pages.yml`](.github/workflows/pages.yml). Local Jekyll
preview is optional and requires Ruby; it is not needed to deploy the site.