---
layout: default
title: "Welcome"
---

# Welcome to My Documentation

Quick links to get started:

## Documentation
- [Installation](/docs/installation)
- [Getting Started](/docs/getting-started)
- [Troubleshooting](/docs/troubleshooting)

## Recent Blog Posts
{% for post in site.posts limit:3 %}
- [{{ post.title }}]({{ post.url }}) - {{ post.date | date: "%B %d" }}
{% endfor %}

[See all posts →](/blog/)