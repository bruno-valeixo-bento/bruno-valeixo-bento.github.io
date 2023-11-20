---
layout: page
title: Research
permalink: /research/
description: >
  My work is mainly focused on String Theory and Cosmology. I am interested in connecting the high-energy physics of strings to the low-energy observations we want to explain: this includes for example the mysterious dark energy and dark matter that dominate the Universe around us (e.g. in the context of the debate around de Sitter vacua in string theory). I usually do this by exploring compactifications of the extra dimensions of string theory in the presence of things like fluxes and branes, which can have interesting effects – an example is the warping that was the basis of my PhD studies in Liverpool. More recently I have started to think more carefully about the Swampland conjectures and their interplay with the familiar reasoning and intuition of Effective Field Theories.
  <br><br>
  Here you can find details about my work, not only more details on the research topics I'm interested in but also the actual projects I have either worked on or are currently thinking about. 
nav: true
nav_order: 1
display_categories: [Topics, Projects]
horizontal: false
---

<!-- pages/projects.md -->
<div class="projects">
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
