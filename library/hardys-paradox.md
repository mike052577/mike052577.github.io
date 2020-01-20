---
layout: cv
title: Library
format: kjhealy
date: 2020/01/20
---



## Hardy's Paradox

This list was last updated on {{ page.date }}.

{% assign documentsByYear = site.data.hardys-paradox | sort: "year" %}

{% for document in documentsByYear %}
  `{{ document.year }}`
  __{{ document.title }}__<br/>
  {{ document.leadauthor }}{% if document.trailauthor != "" %} – {{ document.trailauthor }}{% endif %}<br/>
  {% if document.doi != "" %} [{{ document.doi }}](https://doi.org/{{ document.doi }})<br/>[Bibtex](https://api.crossref.org/works/doi:{{ document.doi }}/transform/application/x-bibtex)
  {% elsif document.arxiv != "" %} [{{ document.arxiv }}](https://arxiv.org/abs/{{ document.arxiv }})
  {% elsif document.url != "" %} [{{ document.url }}]({{ document.url }})
  {% endif %}

{% endfor %}




