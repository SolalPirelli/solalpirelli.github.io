---
title: Research
layout: default
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

# My Research Projects

Each project page contains a short blog post summarizing the project's goals, results, and lessons learned.

{% assign sorted_research = site.research | sort_by: "date" | reverse %}
{% for item in sorted_research %}
## [{{ item.title }}](/research/{{ item.slug }})
*{{ item.authors }}*  
{{ item.venue }} {% if item.remarks %}; *{{ item.remarks }}* {% endif %}  
{% if item.doi %} [DOI]({{ item.doi }}) / {% endif %} [Paper]({{ site.baseurl }}/pdf/{{ item.slug }}.pdf) / [Artifact]({{ item.artifact }}) {% if item.video %} / [Video]({{ item.video }}) {% endif %}
{% endfor %}


# Projects I've collaborated in

These are projects I was involved in but did not lead.  
They're still cool, you should check them out!

{% for item in page.others %}
## {{ item.title }}
*{{ item.authors }}*  
{{ item.venue }}  
[DOI]({{ item.doi }}) / [Paper]({{ site.baseurl }}/pdf/{{ item.slug }}.pdf)
{% endfor %}
