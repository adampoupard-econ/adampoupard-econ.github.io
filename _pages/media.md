---
layout: page
permalink: /media/
title: Media
description: Media appearances, interviews, podcasts, and public contributions by Adam Poupard.
nav: true
nav_order: 3
---

Selected interviews, public talks, and written contributions.

{% for item in site.data.media %}

<div class="row align-items-start">
  {% if item.image %}
    <div class="col-sm-3 mb-3 mb-sm-0">
      <a href="{{ item.url }}" target="_blank" rel="noopener noreferrer" aria-label="Open {{ item.title | escape }}">
        <img src="{{ item.image | relative_url }}" class="img-fluid rounded" alt="Preview for {{ item.title | escape }}" loading="lazy">
      </a>
    </div>
  {% endif %}
  <div class="{% if item.image %}col-sm-9{% else %}col-12{% endif %}">
    <h2 class="mt-0">{{ item.title }}</h2>

    <p><strong>{{ item.outlet }}</strong> · {{ item.date }} · {{ item.format }}</p>

    <p>{{ item.description }}</p>

    <p>
      <a href="{{ item.url }}" target="_blank" rel="noopener noreferrer">{{ item.link_label | default: "View the contribution" }}</a>
      {% if item.pdf_url %}
        · <a href="{{ item.pdf_url | relative_url }}" target="_blank" rel="noopener noreferrer">{{ item.pdf_label | default: "Read the PDF" }}</a>
      {% endif %}
    </p>

    {% if item.youtube_id %}
      <div class="ratio ratio-16x9 my-4">
        <iframe
          src="https://www.youtube-nocookie.com/embed/{{ item.youtube_id }}"
          title="{{ item.title }}"
          loading="lazy"
          referrerpolicy="strict-origin-when-cross-origin"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
          allowfullscreen
        ></iframe>
      </div>
    {% endif %}

  </div>
</div>

{% unless forloop.last %}---{% endunless %}
{% endfor %}
