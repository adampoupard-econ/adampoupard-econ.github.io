---
layout: page
permalink: /teaching/
title: Teaching
description: Courses and modules taught by Adam Poupard.
nav: true
nav_order: 5
---

{% for course in site.data.teaching %}

## {{ course.title }}

{% if course.institution %}
**{{ course.institution }}** · {{ course.period }} · {{ course.role }}
{% else %}
**{{ course.student }}** · {{ course.period }} · {{ course.role }}
{% endif %}

{{ course.description }}

{% if course.modules %}
**Modules taught:** {{ course.modules | join: ", " }}
{% endif %}

{% if course.url %}[Course catalogue]({{ course.url }}){:target="_blank" rel="noopener noreferrer"}{% endif %}

{% unless forloop.last %}---{% endunless %}
{% endfor %}
