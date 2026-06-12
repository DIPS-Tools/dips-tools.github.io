---
layout: page
permalink: /people/
title: people
description: members of the DIPS Lab
nav: true
nav_order: 7
---

<!-- Members are defined in _data/people.yml -->

<style>
  .people-grid {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
  }
  .people-card {
    flex: 0 0 25%; /* 4 members per row */
    max-width: 25%;
    padding: 0 0.5rem;
    margin-top: 2rem;
    text-align: center;
  }
  @media (max-width: 768px) {
    .people-card {
      flex: 0 0 50%; /* 2 per row on small screens */
      max-width: 50%;
    }
  }
  .people-card .person-name {
    margin-top: 1rem;
    margin-bottom: 0.25rem;
    font-size: 1.1rem;
    font-weight: 500;
    white-space: nowrap; /* keep the name on one line */
  }
  .people-card .person-role {
    margin-bottom: 0.25rem;
  }
  .people-card .person-links {
    margin-bottom: 0;
    font-size: 3em; /* icon size */
  }
  .people-card .person-links a {
    margin: 0 0.25rem;
  }
</style>

{% for group in site.data.people %}

<h2 class="mt-4">{{ group.group }}</h2>

<div class="people-grid">
  {% for member in group.members %}
    <div class="people-card">
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
      <h5 class="person-name">{{ member.name }}</h5>
      <p class="person-role">{{ member.role }}</p>
      <p class="person-links">
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
