---
layout: page
permalink: /cv/
title: CV
nav: true
nav_order: 5
description: research, engineering experience, education, and selected manuscripts.
---

[Download CV (PDF)]({{ '/assets/pdf/cv.pdf' | relative_url }})

{% assign cv = site.data.cv.cv %}

{{ cv.summary }}

## Education

{% for entry in cv.sections.Education %}

### {{ entry.institution }}

**{{ entry.studyType }} in {{ entry.area }}**<br>
{{ entry.start_date }} - {{ entry.end_date }} · {{ entry.location }} · GPA: {{ entry.score }}
{% endfor %}

## Experience

{% for entry in cv.sections.Experience %}

### {{ entry.company }}

**{{ entry.position }}**<br>
{{ entry.start_date }} - {{ entry.end_date | capitalize }} · {{ entry.location }}

{% if entry.summary %}{{ entry.summary }}{% endif %}
{% for highlight in entry.highlights %}

- {{ highlight }}
  {% endfor %}
  {% endfor %}

## Selected Manuscripts

{% for entry in cv.sections["Selected Manuscripts"] %}

- [{{ entry.title }}]({{ entry.url }})<br>
  {{ entry.summary }}
  {% endfor %}

## Technical Skills

{% for entry in cv.sections.Skills %}
**{{ entry.name }}:** {{ entry.keywords }}

{% endfor %}

## PDF Version

<iframe
  title="Xiwen Chen's curriculum vitae"
  src="{{ '/assets/pdf/cv.pdf' | relative_url }}"
  width="100%"
  height="900"
  loading="lazy"
  style="border: 1px solid #ddd;"
></iframe>

[Open the PDF directly]({{ '/assets/pdf/cv.pdf' | relative_url }}) if the embedded viewer is unavailable.
