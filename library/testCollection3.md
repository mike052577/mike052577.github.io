---
layout: cv
title: Library
format: kjhealy
date: 2019/06/01
---



## Test Collection of References

This list was last updated on {{ page.date }}.

{% assign documentsByYear = site.data.testCollection3 | sort: "year" %}

{% for document in documentsByYear %}
  `{{ document.year }}`
  __{{ document.title }}__<br/>
  {{ document.leadauthor }}{% if document.trailauthor != "" %} – {{ document.trailauthor }}{% endif %}<br/>
  {% if document.doi != "" %} [{{ document.doi }}](https://doi.org/{{ document.doi }})<br/>[Bibtex](https://api.crossref.org/works/doi:{{ document.doi }}/transform/application/x-bibtex)
  {% elsif document.arxiv != "" %} [{{ document.arxiv }}](https://arxiv.org/abs/{{ document.arxiv }})
  {% endif %}

{% endfor %}




