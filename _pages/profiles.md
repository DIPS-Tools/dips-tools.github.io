---
layout: page
permalink: /people/
title: people
description: members of the DIPS Lab
nav: true
nav_order: 7
---

<!-- Members are defined in _data/people.yml -->
{% for group in site.data.people %}

<h2 class="mt-4">{{ group.group }}</h2>

<div class="row row-cols-2 row-cols-md-4 justify-content-center">
  {% for member in group.members %}
    <div class="col text-center mt-4">
      {% if member.image %}
        <img
          src="{{ member.image | relative_url }}"
          alt="{{ member.name }}"
          class="rounded-circle z-depth-1"
          style="width: 140px; height: 140px; object-fit: cover;"
        >
      {% else %}
        {% assign name_parts = member.name | remove: 'Prof. ' | remove: 'Dr. ' | split: ' ' %}
        <div
          class="rounded-circle z-depth-1 d-flex align-items-center justify-content-center"
          style="width: 140px; height: 140px; margin: 0 auto; background-color: var(--global-divider-color); color: var(--global-text-color); font-size: 2.5rem;"
        >
          {{ name_parts.first | slice: 0 }}{{ name_parts.last | slice: 0 }}
        </div>
      {% endif %}
      <h5 class="mt-3 mb-1">{{ member.name }}</h5>
      <p class="mb-1">{{ member.role }}</p>
      <p class="mb-0">
        {% if member.website %}
          <a href="{{ member.website }}" target="_blank" rel="noopener noreferrer" title="Personal website"><i class="fa-solid fa-globe"></i></a>
        {% endif %}
        {% if member.scholar %}
          <a href="{{ member.scholar }}" target="_blank" rel="noopener noreferrer" title="Google Scholar"><i class="ai ai-google-scholar"></i></a>
        {% endif %}
      </p>
    </div>
  {% endfor %}
</div>
{% endfor %}
