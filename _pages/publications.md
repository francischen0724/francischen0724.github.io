---
layout: page
permalink: /publications/
title: publications
description: research publications, manuscripts, and technical reports.
nav: true
nav_order: 2
---

<!-- _pages/publications.md -->

Research manuscripts and publications. For methods, experiments, and engineering contributions, see [Projects]({{ '/projects/' | relative_url }}).

<!-- Bibsearch Feature -->

{% include bib_search.liquid %}

<div class="publications">

{% bibliography %}

</div>

## Manuscripts

Additional manuscripts, project reports, and a book chapter contribution.

<div class="publications">
  <ol class="bibliography">
    {% for manuscript in site.data.manuscripts %}
    <li>
      <div class="row">
        <div class="col col-sm-2 abbr">
          <abbr class="badge rounded w-100">{{ manuscript.type | escape }}</abbr>
        </div>
        <div id="{{ manuscript.id }}" class="col-sm-8">
          <div class="title">{{ manuscript.title | escape }}</div>
          {% if manuscript.authors %}
          <div class="author">
            {%- for author in manuscript.authors -%}
              {%- unless forloop.first -%}, {% endunless -%}
              {%- if author == 'Xiwen Chen' -%}<em>{{ author }}</em>{%- else -%}{{ author | escape }}{%- endif -%}
            {%- endfor -%}
          </div>
          {% endif %}
          <div class="periodical"><em>{{ manuscript.status | escape }}</em></div>
          {% if manuscript.note %}<div class="periodical">{{ manuscript.note | escape }}</div>{% endif %}
          <div class="links">
            <a href="{{ manuscript.pdf | relative_url }}" class="btn btn-sm z-depth-0" role="button" target="_blank" rel="noopener" aria-label="Read PDF: {{ manuscript.title | escape }}">
              <i class="fa-solid fa-file-pdf" aria-hidden="true"></i> PDF
            </a>
            {% if manuscript.code %}
            <a href="{{ manuscript.code }}" class="btn btn-sm z-depth-0" role="button" target="_blank" rel="noopener" aria-label="GitHub repository: {{ manuscript.title | escape }}{% if manuscript.code_private %} (access required){% endif %}">
              <i class="fa-brands fa-github" aria-hidden="true"></i> {% if manuscript.code_private %}Code (private){% else %}Code{% endif %}
            </a>
            {% endif %}
          </div>
        </div>
      </div>
    </li>
    {% endfor %}
  </ol>
</div>
