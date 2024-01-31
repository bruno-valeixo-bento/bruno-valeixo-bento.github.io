---
layout: page
title: Research
permalink: /research/
description: >
nav: true
nav_order: 1
display_categories: [Topics, Projects]
horizontal: false
---

<!-- pages/projects.md -->
<div class="projects">

Broadly speaking, I work on <span style="font-weight: bold">high energy physics, gravity and cosmology</span>. I am interested in how the Universe works at the most fundamental level, including what it is made of (particles? strings?) and which interactions keep it together &mdash; gravity being the sneakiest of them all. In a nutshell, a day in my life includes
  <ul style="list-style-type:none; line-height:180%; padding-top:1em  ">
    <li>String Theory / Supergravity</li>
    <li>Cosmology / Dark Energy / Inflation</li>
    <li>Effective Field Theories</li>
  </ul>
  I have also worked on Causal Set Theory in the past, but it's been a while. You can find more details about my work, not only on the research topics I'm interested in but also the actual projects I have either worked on or are currently on my mind. 

{%- if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_projects = site.projects | where: "category", category -%}
  {%- assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
  {% endfor %}

{%- else -%}
<!-- Display projects without categories -->
  {%- assign sorted_projects = site.projects | sort: "importance" -%}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
{%- endif -%}
</div>
