---
layout: cv
title: Library
---



This is the default library page, and will contain links to topic collections.

Let's see if headers and links work together.



{% assign documentsByYear = site.data.testRefCollection | sort: "year" %}

{% for document in documentsByYear %}
  `{{ document.year }}`<br/>
  __{{ document.title }}__<br/>
  {{ document.leadauthor }} - {{ document.trailauthor }}<br/>
  {% if document.doi != "" %}
    <a href="https://doi.org/{{ document.doi }}" >{{ document.doi }}</a><br/>
    <a href="https://api.crossref.org/works/doi:{{ document.doi }}/transform/application/x-bibtex" >Bibtex</a>
  {% elsif document.arxiv != "" %}
    <a href="https://arxiv.org/abs/{{ document.arxiv }}" >{{ document.arxiv }}</a>
  {% endif %}

{% endfor %}





