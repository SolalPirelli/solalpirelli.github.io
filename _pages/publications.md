---
title: Publications
permalink: /publications/
collection: publications
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

{% assign sorted_publications = site.publications | sort_by: "date" | reversed %}
{% for pub in sorted_publications %}
  **{{ pub.title }}** <br>
  *{{ pub.authors }}* <br>
  {{ pub.venue }} {% if pub.remarks %}; *{{ pub.remarks }}* {% endif %} <br>
  [DOI]({{ pub.doi }}) / [Paper](./pdf/{{ pub.slug }}.pdf) / [Artifact]({{ pub.artifact }}) / [Video]({{ pub.video }})
{% endfor %}


## Others

{% for pub in page.others %}
  **{{ pub.title }}** <br>
  *{{ pub.authors }}* <br>
  {{ pub.venue }} <br>
  [DOI]({{ pub.doi }}) / [Paper](./pdf/{{ pub.slug }}.pdf)
{% endfor %}
