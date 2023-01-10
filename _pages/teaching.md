---
layout: page
permalink: /teaching/
title: Teaching
img: 
description: 
nav: true
---

<!-- _pages/publications.md -->
<div class="publications">

{%- for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f teaching -q @*[year={{y}}]* %}
{% endfor %}
