---
layout: page
title: Team
permalink: /team/
description: Meet the members of our working group.
nav_order: 5
---

{% assign pi = site.data.members | where: "role", "pi" %}
{% assign postdocs = site.data.members | where: "role", "postdoc" %}
{% assign phd = site.data.members | where: "role", "phd" %}
{% assign masters = site.data.members | where: "role", "masters" %}
{% assign alumni = site.data.members | where: "role", "alumni" %}

<!-- ==================== PI / Group Leader ======================== -->
{% if pi.size > 0 %}
## Group Leader

<div class="row g-4 mb-5">
  {% for member in pi %}
  <div class="col-12 col-sm-6 col-md-4 col-lg-3">
    {% include member_card.html member=member %}
  </div>
  {% endfor %}
</div>
{% endif %}

<!-- ==================== Postdocs ================================= -->
{% if postdocs.size > 0 %}
## Postdoctoral Researchers

<div class="row g-4 mb-5">
  {% for member in postdocs %}
  <div class="col-12 col-sm-6 col-md-4 col-lg-3">
    {% include member_card.html member=member %}
  </div>
  {% endfor %}
</div>
{% endif %}

<!-- ==================== PhD Students ============================ -->
{% if phd.size > 0 %}
## PhD Students

<div class="row g-4 mb-5">
  {% for member in phd %}
  <div class="col-12 col-sm-6 col-md-4 col-lg-3">
    {% include member_card.html member=member %}
  </div>
  {% endfor %}
</div>
{% endif %}

<!-- ==================== Master's Students ======================== -->
{% if masters.size > 0 %}
## Master's Students

<div class="row g-4 mb-5">
  {% for member in masters %}
  <div class="col-12 col-sm-6 col-md-4 col-lg-3">
    {% include member_card.html member=member %}
  </div>
  {% endfor %}
</div>
{% endif %}

<!-- ==================== Alumni =================================== -->
{% if alumni.size > 0 %}
## Alumni

<div class="row g-4 mb-4">
  {% for member in alumni %}
  <div class="col-12 col-sm-6 col-md-4 col-lg-3">
    {% include member_card.html member=member %}
  </div>
  {% endfor %}
</div>
{% endif %}

{% if site.data.members.size == 0 %}
<p class="text-muted">Team members will appear here. Add entries to <code>_data/members.yml</code>.</p>
{% endif %}

---

## Join Us

We are always looking for motivated students and researchers to join our group. If you are interested in [your research area] and would like to work with us, please send your CV and a brief statement of research interests to [{{ site.author.email }}](mailto:{{ site.author.email }}).
