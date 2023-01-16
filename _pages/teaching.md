---
layout: page
permalink: /teaching/
title: Teaching
img: 
years: [2023, 2022]
description: Taught SP and ML courses
nav: true
---

<!-- _pages/publications.md -->
<div class="publications">

{%- for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f teaching -q @*[year={{y}}]* %}
{% endfor %}
