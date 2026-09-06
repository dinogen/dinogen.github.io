# context
# Repository Guide

This repository is a planned personal publishing system. Keep the canonical
article in Markdown, then derive platform-specific drafts from it. Do not
assume that planned automation exists: currently there are no scripts, tests,
site generator, CI workflow, or dependency manifest in the checkout.

## Index

- [README.md](README.md): repository entry point; currently minimal.
- [system_description.md](system_description.md): editorial strategy, proposed
	content model, publication workflow, and implementation roadmap.
- [.gitignore](.gitignore): ignored Python environments, build output, and
	generated artifacts.
- `contents/`: canonical article Markdown intended for the website. Currently
	empty.
- `generated/`: generated drafts for LinkedIn, X, and Instagram. Currently
	empty.
- `ideas/`: low-friction idea inbox. Currently empty.
- `images/`: visual assets. Currently empty.
- `scripts/`: future automation. Currently empty.
- `ai-friendly-docs/`: repository documentation for agents and contributors.
	Add focused documents here when the project gains enough complexity to need
	them, then link them from this file.

## Working Rules

- Treat `contents/` as the source of truth; generated social copy must not
	replace or silently rewrite the canonical article.
- Preserve the author's insight when adapting content for a platform. Human
	review is required before publication.
- Keep company-sensitive or confidential information out of articles and
	generated drafts.
- Use the existing Markdown and directory conventions before introducing a
	framework or new metadata schema. Document new conventions here and in the
	relevant project document.
- Use the local `venv/` only for exploratory or future Python tooling. It is
	ignored and is not a reproducible dependency specification.
- Do not invent build, test, deployment, or social-publishing commands. First
	add and document the supporting tooling, then update this guide.
- Update this guide when directory ownership, workflow stages, or runnable
	commands change.

## Current Workflow

The intended editorial flow is:

`idea -> draft -> review -> canonical Markdown -> platform adaptations -> human approval -> publication`

The intended website and social integrations are described in
[system_description.md](system_description.md), but are not implemented yet.

## Plans

Plans use numbered tasks with these subsections:

- Description
- Aim
- Context
- Measurable results
- Todo list
