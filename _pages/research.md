---
layout: page
title: Research
permalink: /research/
description:
nav: true
nav_order: 1
---

My research focuses on control and estimation for resilient ship–shore communication systems and autonomous maritime applications.
I develop sliding-mode, adaptive and fault-tolerant control and nonlinear estimation methods for time-varying, uncertain, multi-channel
environments, so that remote situational awareness stays reliable.

## Research Areas

<div class="research-areas">
  {% for area in site.data.research_interests %}
    <div class="research-area-card">
      <div class="research-area-image">
        <img src="{{ area.image | relative_url }}" alt="{{ area.title }}" loading="lazy">
      </div>
      <div class="research-area-content">
        <h3>{{ area.title }}</h3>
        <p>{{ area.description }}</p>
      </div>
    </div>
  {% endfor %}
</div>

<p class="research-projects-link"><a href="{{ '/projects/' | relative_url }}">View my PhD project →</a></p>
