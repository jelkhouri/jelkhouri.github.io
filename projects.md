---
title: "Projects"
permalink: /projects/
layout: single
---

{% assign sorted_projects = site.projects | sort: "date" | reverse %}
{% for project in sorted_projects %}
## [{{ project.title }}]({{ project.url }})
{{ project.excerpt }}
---
{% endfor %}