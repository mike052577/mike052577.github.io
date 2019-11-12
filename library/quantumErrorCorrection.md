---
layout: cv
title: Library
format: kjhealy
date: 2019/11/12
---



## Quantum Error Correction

This list is formed from its component topics on the [library](/library) main page; please refer to those individual lists for the dates on which they were last updated.

{% assign documentsByYear = site.data.quantumReedMullerCodes | concat: site.data.highDimensionColorCodes | concat: site.data.gaugeFixing | uniq | sort: "year" %}

{% for document in documentsByYear %}
  `{{ document.year }}`
  __{{ document.title }}__<br/>
  {{ document.leadauthor }}{% if document.trailauthor != "" %} – {{ document.trailauthor }}{% endif %}<br/>
  {% if document.doi != "" %} [{{ document.doi }}](https://doi.org/{{ document.doi }})<br/>[Bibtex](https://api.crossref.org/works/doi:{{ document.doi }}/transform/application/x-bibtex)
  {% elsif document.arxiv != "" %} [{{ document.arxiv }}](https://arxiv.org/abs/{{ document.arxiv }})
  {% endif %}

{% endfor %}





