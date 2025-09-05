---
layout: home
title: Welcome to My Blog
---

# Welcome to My Blog

This is my personal blog where I share articles on various topics.

{% for post in site.posts %}
- [{{ post.title }}]({{ post.url }}) - {{ post.date | date: "%b %-d, %Y" }}
{% endfor %}
