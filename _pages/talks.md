---
layout: page
permalink: /talks/
title: Talks
img: assets/img/eusipco_talk.jpg
description: Some selected talks
years: [2022, 2021, 2020, 2019]
nav: true
---

{%- if page.img -%}
  {%- include figure.html 
    path=page.img -%}
{%- endif -%}

<!-- _pages/publications.md -->
<div class="publications">

{%- for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f talks -q @*[year={{y}}]* %}
{% endfor %}

</div>