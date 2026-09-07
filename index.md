---
title: Professional AI Programmer
description: Shared thoughts about software engineering, AI and the future of development.
---

Welcome. This is a small, evolving knowledge base about software engineering,
AI, data, architecture and legacy systems.

## Articles

{% assign articles = site.contents | sort: "date" | reverse %}
{% for article in articles %}
### [{{ article.title }}]({{ article.url | relative_url }})

{{ article.excerpt | strip_html | strip_newlines | truncate: 180 }}

{% endfor %}
