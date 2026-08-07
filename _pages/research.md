---
layout: page
permalink: /research/
title: Research
description: Scientific publications and working papers by Adam Poupard.
nav: true
nav_order: 2
images:
  lightbox2: true
---

My research lies at the intersection of ecological economics, political economy, biodiversity policy, and food systems. Links below point to the official publication record; language-specific PDFs are shown when they are publicly available.

{% for paper in site.data.research %}

<div class="row align-items-start">
  {% if paper.image %}
    <div class="col-sm-3 mb-3 mb-sm-0">
      <a
        href="{{ paper.image | relative_url }}"
        data-lightbox="research-publications"
        data-title="{{ paper.title | escape }}"
        aria-label="Enlarge preview for {{ paper.title | escape }}"
      >
        <img src="{{ paper.image | relative_url }}" class="img-fluid rounded" alt="Preview for {{ paper.title | escape }}">
      </a>
    </div>
  {% endif %}
  <div class="{% if paper.image %}col-sm-9{% else %}col-12{% endif %}">
    <h2 class="mt-0">{{ paper.title }}</h2>

    <p><strong>{{ paper.authors }}</strong> ({{ paper.year }}). <em>{{ paper.venue }}</em>{% if paper.reference %}, {{ paper.reference }}{% endif %}.</p>

    <p>{{ paper.summary }}</p>

    <p>
      <a href="{{ paper.official_url }}" target="_blank" rel="noopener noreferrer">Official publication</a>
      {% for pdf in paper.pdfs %}
        · <a href="{{ pdf.url }}" target="_blank" rel="noopener noreferrer">PDF — {{ pdf.language }}</a>
      {% endfor %}
    </p>

  </div>
</div>

{% unless forloop.last %}---{% endunless %}
{% endfor %}
