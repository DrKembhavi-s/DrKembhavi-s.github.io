---
layout: default
title: Welcome to My Blog
---

# Welcome to {{ site.title }}

Here are my latest articles:

<ul>
{% for post in site.posts %}
  <li><a href="{{ post.url }}">{{ post.title }}</a> - {{ post.date | date: "%b %-d, %Y" }}</li>
{% endfor %}
</ul>
