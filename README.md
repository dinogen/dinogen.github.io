# dinogen.github.io

Personal publishing system for sharing practical lessons from software
engineering, AI, data, banking software, legacy systems, architecture, and
programming.

The project is built around a simple principle: write the insight once, keep
the original article as the source of truth, and adapt it for the website and
social platforms only after human review.

## Status

This repository is currently documentation-first. The content structure is in
place, but the website generator, content transformation scripts, tests, CI,
and social publishing integrations have not been implemented yet.

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

Until those pieces exist, do not assume that build, test, deployment, or
publishing commands are available in this repository.