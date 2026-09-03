---
layout: page
permalink: /publications/
title: Publications
description: My publications in reverse chronological order.
nav: true
nav_order: 2
---
<!-- _pages/publications.md -->
<div class="publications">

{%- comment -%}
Years are derived from the current date rather than hardcoded, and a year with no
entries prints nothing -- so a new paper never needs this file edited to show up.
{%- endcomment -%}
{%- assign latest_year = site.time | date: "%Y" | plus: 1 -%}
{%- for y in (2019..latest_year) reversed %}
  {%- capture bib %}{% bibliography -f papers -q @*[year={{y}}]* %}{% endcapture -%}
  {%- if bib contains "<li" %}
  <h2 class="year">{{y}}</h2>
  {{ bib }}
  {%- endif -%}
{% endfor %}

</div>
