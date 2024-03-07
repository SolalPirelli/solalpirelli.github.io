---
title: Guides
layout: default
---

# Guides

{% assign sorted_guides = site.guides | sort_by: "order" | reverse %}
{% for item in sorted_guides %}
## [{{ item.title }}](/guides/{{ item.slug }})
{{ item.description }}
{% endfor %}
