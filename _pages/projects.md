---
layout: page
title: Projects
permalink: /projects/
description:
nav: true
nav_order: 2
---

<!-- Full-width project cards (custom markup: the theme's horizontal cards rely on Bootstrap grid classes, which are disabled). -->
<div class="project-list">
  {% assign sorted_projects = site.projects | sort: "importance" %}
  {% for project in sorted_projects %}
    <a class="project-wide-card" href="{% if project.redirect %}{{ project.redirect }}{% else %}{{ project.url | relative_url }}{% endif %}">
      {% if project.img %}
        <img src="{{ project.img | relative_url }}" alt="{{ project.title }}" loading="eager">
      {% endif %}
      <div class="project-wide-card-body">
        <h2>{{ project.title }}</h2>
        <p>{{ project.description }}</p>
        <span class="project-wide-card-more">Read more →</span>
      </div>
    </a>
  {% endfor %}
</div>
