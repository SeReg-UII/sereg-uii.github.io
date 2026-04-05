---
layout: page
title: Publications
permalink: /publications/
description: Full list of publications from the working group.
nav_order: 3
---

{% assign pubs_by_year = site.data.publications | group_by: "year" | sort: "name" | reverse %}

{% for year_group in pubs_by_year %}
## {{ year_group.name }}

<div class="pub-list mb-4">
  {% for pub in year_group.items %}
  <div class="pub-entry d-flex align-items-start gap-3 mb-4 pb-4 border-bottom">
    {% if pub.preview %}
    <img src="{{ pub.preview | relative_url }}" alt="{{ pub.title }}"
         class="pub-thumb flex-shrink-0 rounded" />
    {% endif %}
    <div class="pub-info">
      <p class="pub-title fw-semibold mb-1">{{ pub.title }}</p>
      <p class="pub-authors text-muted small mb-1">{{ pub.authors }}</p>
      <p class="pub-venue small mb-2">
        <em>{{ pub.venue }}</em>{% if pub.year %}, {{ pub.year }}{% endif %}
        {% if pub.award %}
        <span class="badge bg-warning text-dark ms-2">
          <i class="fas fa-trophy me-1"></i>{{ pub.award }}
        </span>
        {% endif %}
      </p>
      <div class="pub-links d-flex flex-wrap gap-2">
        {% if pub.pdf %}
        <a href="{{ pub.pdf }}" class="btn btn-xs btn-outline-danger" target="_blank" rel="noopener">
          <i class="fas fa-file-pdf me-1"></i>PDF
        </a>
        {% endif %}
        {% if pub.url %}
        <a href="{{ pub.url }}" class="btn btn-xs btn-outline-primary" target="_blank" rel="noopener">
          <i class="fas fa-external-link-alt me-1"></i>Paper
        </a>
        {% endif %}
        {% if pub.code %}
        <a href="{{ pub.code }}" class="btn btn-xs btn-outline-dark" target="_blank" rel="noopener">
          <i class="fab fa-github me-1"></i>Code
        </a>
        {% endif %}
        {% if pub.project %}
        <a href="{{ pub.project }}" class="btn btn-xs btn-outline-secondary" target="_blank" rel="noopener">
          <i class="fas fa-globe me-1"></i>Project
        </a>
        {% endif %}
      </div>
    </div>
  </div>
  {% endfor %}
</div>
{% endfor %}

{% if site.data.publications.size == 0 %}
<p class="text-muted">Publications will appear here. Add entries to <code>_data/publications.yml</code>.</p>
{% endif %}
