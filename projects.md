---
title: "Projects"
permalink: /projects/
layout: single
---

{% assign sorted_projects = site.projects | sort: "date" | reverse %}
{% for project in sorted_projects %}
<div class="project-entry">
  {% if project.thumbnail %}
  <a href="{{ project.url }}" class="project-entry__thumbnail">
    <img src="{{ project.thumbnail | relative_url }}" alt="{{ project.title }}">
  </a>
  {% endif %}
  <div class="project-entry__body">
    <h2><a href="{{ project.url }}">{{ project.title }}</a></h2>
    <p>{{ project.excerpt }}</p>
  </div>
</div>
{% endfor %}