---
layout: page
title: Categories
---

# Blog Categories

## Academic
{% for post in site.categories.Academic %}
- [{{ post.title }}]({{ post.url }}) - {{ post.date | date: "%B %d, %Y" }}
{% endfor %}

## Research
{% for post in site.categories.Research %}
- [{{ post.title }}]({{ post.url }}) - {{ post.date | date: "%B %d, %Y" }}
{% endfor %}
