---
layout: page
permalink: /tools/
title: tools
description: Open tools from the DIPS Lab for data sharing, policy, negotiation, trust and consent.
nav: true
nav_order: 5
---

<!-- Tools are defined in _data/tools.yml -->

<style>
  .tools-grid {
    display: flex;
    flex-wrap: wrap;
    margin: 1.5rem -0.75rem 0;
  }
  .tool-cell {
    flex: 0 0 50%;
    max-width: 50%;
    padding: 0.75rem;
  }
  @media (max-width: 768px) {
    .tool-cell {
      flex: 0 0 100%;
      max-width: 100%;
    }
  }
  .tool-card {
    position: relative;
    height: 100%;
    padding: 1.5rem;
    border: 1px solid var(--global-divider-color);
    border-radius: 8px;
    background-color: var(--global-card-bg-color);
    transition: box-shadow 0.2s ease, transform 0.2s ease;
  }
  a.tool-card {
    display: block;
    color: inherit;
    text-decoration: none;
  }
  a.tool-card:hover {
    box-shadow: 0 4px 20px 0 rgba(0, 0, 0, 0.1);
    transform: translateY(-2px);
    color: inherit;
  }
  .tool-card .tool-icon {
    font-size: 2.5rem;
    line-height: 1;
  }
  .tool-card .tool-name {
    margin: 0.75rem 0 0.5rem;
    font-size: 1.2rem;
    font-weight: 500;
  }
  .tool-card .tool-name .tool-arrow {
    color: var(--global-theme-color);
  }
  .tool-card .tool-desc {
    margin: 0;
    color: var(--global-text-color-light);
  }
</style>

{% for group in site.data.tools %}

<h2 class="mt-4">{{ group.category }}</h2>

<div class="tools-grid">
  {% for tool in group.tools %}
    {% if tool.url %}
      <div class="tool-cell">
        <a class="tool-card" href="{{ tool.url }}" target="_blank" rel="noopener noreferrer">
          <div class="tool-icon">{{ tool.icon }}</div>
          <h3 class="tool-name">{{ tool.name }} <span class="tool-arrow">&rarr;</span></h3>
          <p class="tool-desc">{{ tool.description }}</p>
        </a>
      </div>
    {% else %}
      <div class="tool-cell">
        <div class="tool-card">
          <div class="tool-icon">{{ tool.icon }}</div>
          <h3 class="tool-name">{{ tool.name }}</h3>
          <p class="tool-desc">{{ tool.description }}</p>
        </div>
      </div>
    {% endif %}
  {% endfor %}
</div>
{% endfor %}
