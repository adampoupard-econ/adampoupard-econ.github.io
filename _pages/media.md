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

## {{ item.title }}

**{{ item.outlet }}** · {{ item.date }} · {{ item.format }}

{{ item.description }}

[{{ item.link_label | default: "View the contribution" }}]({{ item.url }}){:target="_blank" rel="noopener noreferrer"}

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

{% unless forloop.last %}---{% endunless %}
{% endfor %}
