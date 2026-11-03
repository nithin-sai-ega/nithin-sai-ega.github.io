---
layout: page
title: Projects
permalink: /projects/
description: Selected projects.
nav: true
nav_order: 2
---

<style>
  /* Project cards: fixed-size grid, centered and slightly wider than the text column.
     The width is capped, so large monitors get the same size cards as laptops. */
  .project-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(min(100%, 300px), 344px));
    justify-content: center;
    gap: 24px;
    width: min(1080px, calc(100vw - 4rem));
    position: relative;
    left: 50%;
    transform: translateX(-50%);
    margin-top: 1.5rem;
  }

  .project-card {
    display: flex;
    flex-direction: column;
    min-height: 340px;
    padding: 1.75rem;
    border: 1px solid var(--global-divider-color);
    border-radius: 12px;
    background-color: var(--global-card-bg-color);
    color: var(--global-text-color);
    transition:
      transform 0.15s ease,
      box-shadow 0.15s ease,
      border-color 0.15s ease;
  }

  .project-card:hover {
    transform: translateY(-3px);
    border-color: var(--global-theme-color);
    box-shadow: 0 8px 24px rgba(0, 0, 0, 0.12);
    color: var(--global-text-color);
    text-decoration: none;
  }

  .project-card h2 {
    margin: 0 0 0.75rem;
    font-size: 1.5rem;
    line-height: 1.25;
  }

  .project-card p {
    margin: 0;
    color: var(--global-text-color-light);
    line-height: 1.55;
  }

  .project-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    margin-top: auto;
    padding-top: 1.5rem;
  }

  .project-tag {
    padding: 0.2rem 0.7rem;
    border-radius: 999px;
    border: 1px solid color-mix(in srgb, var(--global-theme-color) 45%, transparent);
    background-color: color-mix(in srgb, var(--global-theme-color) 10%, transparent);
    color: var(--global-theme-color);
    font-size: 0.8rem;
    line-height: 1.5;
    white-space: nowrap;
  }

  @media (max-width: 640px) {
    .project-card {
      min-height: 0;
    }
  }
</style>

{% assign sorted_projects = site.projects | sort: "importance" %}

<div class="project-grid">
  {% for project in sorted_projects %}
  <a class="project-card" href="{{ project.url | relative_url }}">
    <h2>{{ project.title }}</h2>
    <p>{{ project.summary | default: project.description }}</p>
    {% if project.tech.size > 0 %}
    <div class="project-tags">
      {% for tool in project.tech %}<span class="project-tag">{{ tool }}</span>{% endfor %}
    </div>
    {% endif %}
  </a>
  {% endfor %}
</div>
