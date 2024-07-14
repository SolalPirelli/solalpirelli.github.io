---
title: Guides
---

{% assign sorted_guides = site.guides | sort_by: "order" | reverse %}
{% for item in sorted_guides %}
{% unless item.hidden %}
## [{{ item.title }}](/guides/{{ item.slug }})
{{ item.description }}
{% endunless %}
{% endfor %}
