---
layout: page
permalink: /repositories/
title: repositories
description: Open-source tools and software from the DIPS Lab, hosted on the DIPS-Tools GitHub organisation.
nav: true
nav_order: 4
---

## GitHub Organisation

<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-start align-items-center">
  <div class="repo p-2 text-center">
    <a href="https://github.com/DIPS-Tools" target="_blank" rel="noopener noreferrer">
      <img class="rounded z-depth-1" alt="DIPS-Tools" src="https://github.com/DIPS-Tools.png" width="120" height="120">
    </a>
  </div>
  <div class="p-2">
    <h4 class="mb-1"><a href="https://github.com/DIPS-Tools" target="_blank" rel="noopener noreferrer">DIPS-Tools</a></h4>
    <p class="mb-0">The GitHub organisation of the DIPS Lab at the University of Southampton, hosting our open-source tools for data sharing, policy and negotiation.</p>
  </div>
</div>

---

{% if site.data.repositories.github_repos %}

## GitHub Repositories

<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% for repo in site.data.repositories.github_repos %}
    {% include repository/repo.liquid repository=repo %}
  {% endfor %}
</div>
{% endif %}
