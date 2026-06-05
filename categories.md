---
layout: page
title: Categories
---

# Blog Categories

Explore my articles organised by the key areas of Ayurvedic practice and thought:

---

## 🏛️ Administrative

Healthcare management and policy in Ayurvedic institutions — exploring leadership challenges, institutional governance, and systemic improvements.

{% assign admin_posts = site.posts | where_exp: "post", "post.categories contains 'Administrative'" %}
{% if admin_posts.size > 0 %}
{% for post in admin_posts %}
- [{{ post.title }}]({{ post.url }}) — {{ post.date | date: "%B %d, %Y" }}
{% endfor %}
{% else %}
*No articles in this category yet.*
{% endif %}

---

## 📚 Academic

Teaching methodologies, curriculum development, and educational reforms — examining how we can better prepare the next generation of Ayurvedic practitioners.

{% assign academic_posts = site.posts | where_exp: "post", "post.categories contains 'Academic'" %}
{% if academic_posts.size > 0 %}
{% for post in academic_posts %}
- [{{ post.title }}]({{ post.url }}) — {{ post.date | date: "%B %d, %Y" }}
{% endfor %}
{% else %}
*No articles in this category yet.*
{% endif %}

---

## 🩺 Clinical

Patient care approaches, treatment protocols, and clinical practice insights — sharing observations from years of clinical experience and patient interactions.

{% assign clinical_posts = site.posts | where_exp: "post", "post.categories contains 'Clinical'" %}
{% if clinical_posts.size > 0 %}
{% for post in clinical_posts %}
- [{{ post.title }}]({{ post.url }}) — {{ post.date | date: "%B %d, %Y" }}
{% endfor %}
{% else %}
*No articles in this category yet.*
{% endif %}

---

## 🔬 Research

Scientific validation, methodology, and evidence-based approaches — bridging ancient wisdom with modern research to advance Ayurveda's credibility.

{% assign research_posts = site.posts | where_exp: "post", "post.categories contains 'Research'" %}
{% if research_posts.size > 0 %}
{% for post in research_posts %}
- [{{ post.title }}]({{ post.url }}) — {{ post.date | date: "%B %d, %Y" }}
{% endfor %}
{% else %}
*No articles in this category yet.*
{% endif %}

---

## 🤔 Reflections & Musings

Personal observations, philosophical thoughts, and contemplative insights — sharing deeper reflections on life, practice, and the journey of understanding Ayurveda.

{% assign reflections_posts = site.posts | where_exp: "post", "post.categories contains 'Reflections & Musings'" %}
{% if reflections_posts.size > 0 %}
{% for post in reflections_posts %}
- [{{ post.title }}]({{ post.url }}) — {{ post.date | date: "%B %d, %Y" }}
{% endfor %}
{% else %}
*No articles in this category yet.*
{% endif %}

---

## 🧘 Yoga & Wellness

Holistic approaches to health and wellbeing — exploring the interconnection between Yoga, Ayurveda, and comprehensive wellness practices.

{% assign yoga_posts = site.posts | where_exp: "post", "post.categories contains 'Yoga & Wellness'" %}
{% if yoga_posts.size > 0 %}
{% for post in yoga_posts %}
- [{{ post.title }}]({{ post.url }}) — {{ post.date | date: "%B %d, %Y" }}
{% endfor %}
{% else %}
*No articles in this category yet.*
{% endif %}

---

## 📋 Healthcare Policy

Critical analysis of AYUSH policy, regulatory frameworks, institutional governance, and the gap between policy intent and ground-level healthcare delivery — examined through an honest insider lens.

{% assign policy_posts = site.posts | where_exp: "post", "post.categories contains 'Healthcare Policy'" %}
{% if policy_posts.size > 0 %}
{% for post in policy_posts %}
- [{{ post.title }}]({{ post.url }}) — {{ post.date | date: "%B %d, %Y" }}
{% endfor %}
{% else %}
*No articles in this category yet.*
{% endif %}

---

## 🌐 Public Health

Ayurveda's real and potential contribution to India's public health infrastructure — hospital beds, workforce deployment, burden of disease, and the honest arithmetic of what the system delivers at population scale.

{% assign pubhealth_posts = site.posts | where_exp: "post", "post.categories contains 'Public Health'" %}
{% if pubhealth_posts.size > 0 %}
{% for post in pubhealth_posts %}
- [{{ post.title }}]({{ post.url }}) — {{ post.date | date: "%B %d, %Y" }}
{% endfor %}
{% else %}
*No articles in this category yet.*
{% endif %}

---

---

---

## 🌍 Geopolitics and Economy

How global economic forces, supply chains, geopolitical conflicts, and commodity markets shape the conditions of Ayurvedic practice — examining the invisible threads connecting a 21-mile strait in the Persian Gulf to the pharmacy shelf.

{% assign geo_posts = site.posts | where_exp: "post", "post.categories contains 'Geopolitics and Economy'" %}

{% if geo_posts.size > 0 %}

{% for post in geo_posts %}

- [{{ post.title }}]({{ post.url }}) — {{ post.date | date: "%B %d, %Y" }}

{% endfor %}

{% else %}

*No articles in this category yet.*

{% endif %}

---

---
*Browse by month in the [Archives](/archives) or return to [Home](/) for the latest posts.*
