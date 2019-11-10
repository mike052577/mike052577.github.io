---
layout: default
title: Library
documentdata: testRefCollection
---




This is the default library page, and will contain links to topic collections.

Let's see if headers and links work together.



{% assign documentsByYear = site.data.testRefCollection | sort: "year" %}

| Year | Title | First Author | Last Author | Identifier | Bibtex Link |
|:----:| ----- |:------------:|:-----------:|:----------:|:-----------:|
{% for document in documentsByYear %}
  {% if document.doi != "" %}
    | {{ document.year }} | {{ document.title }} | {{ document.leadauthor }} | {{ document.trailauthor }} | <a href="https://doi.org/{{ document.doi }}" >{{ document.doi }}</a> | <a href="https://api.crossref.org/works/doi:{{ document.doi }}/transform/application/x-bibtex" >Bibtex</a> |
  {% elsif document.arxiv != "" %}
    {% assign identifierlink =  %}
    | {{ document.year }} | {{ document.title }} | {{ document.leadauthor }} | {{ document.trailauthor }} | <a href="https://arxiv.org/abs/{{ document.arxiv }}" >{{ document.arxiv }}</a> |   |
  {% else %}
    | {{ document.year }} | {{ document.title }} | {{ document.leadauthor }} | {{ document.trailauthor }} |   |   |
  {% endif %}
{% endfor %}





