---
title: Research
permalink: /research/
collection: research
layout: single
classes: wide
others:
  - title: Verifying Software Network Functions with No Verification Expertise
    venue: SOSP '19
    authors: A. Zaostrovnykh, S. Pirelli, R. Iyer, M. Rizzo, L. Pedrosa, K. Argyraki, G. Candea
    slug: vigor
    doi: https://doi.org/10.1145/3341301.3359647
  - title: Performance Contracts for Software Network Functions
    venue: NSDI '19
    authors: R. Iyer, L. Pedrosa, A. Zaostrovnykh, S. Pirelli, K. Argyraki, G. Candea
    slug: bolt
    doi: https://www.usenix.org/conference/nsdi19/presentation/iyer
  - title: A Formally Verified NAT
    venue: SIGCOMM '17
    authors: A. Zaostrovnykh, S. Pirelli, L. Pedrosa, K. Argyraki, G. Candea
    slug: vignat
    doi: https://doi.org/10.1145/3098822.3098833
---

## My Projects

Click on each project's title for a short blog post summarizing the project's goals, results, and lessons learned.

{% assign sorted_research = site.research | sort_by: "date" | reverse %}
{% for item in sorted_research %}
  **[{{ item.title }}](./{{ item.slug }})** <br>
  *{{ item.authors }}* <br>
  {{ item.venue }} {% if item.remarks %}; *{{ item.remarks }}* {% endif %} <br>
  [DOI]({{ item.doi }}) / [Paper]({{ site.baseurl }}/pdf/{{ item.slug }}.pdf) / [Artifact]({{ item.artifact }}) / [Video]({{ item.video }})
{% endfor %}


## Others

{% for item in page.others %}
  **{{ item.title }}** <br>
  *{{ item.authors }}* <br>
  {{ item.venue }} <br>
  [DOI]({{ item.doi }}) / [Paper]({{ site.baseurl }}/pdf/{{ item.slug }}.pdf)
{% endfor %}
