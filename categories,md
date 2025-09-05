---
layout: page
title: Categories
permalink: /categories/
---

# Blog Categories

## 🏛️ Administrative
Posts about Ayurveda administration and management

## 📚 Academic  
Educational content and teaching materials

## 🩺 Clinical
Patient care and treatment approaches

## 🔬 Research
Latest research and studies in Ayurveda

---

## All Posts by Category

{% for category in site.categories %}
### {{ category[0] }}
<ul>
{% for post in category[1] %}
  <li><a href="{{ post.url }}">{{ post.title }}</a> - {{ post.date | date: "%B %d, %Y" }}</li>
{% endfor %}
</ul>
{% endfor %}
