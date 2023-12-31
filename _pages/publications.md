---
layout: page
title: Publications
permalink: /publications/
years: [2023, 2022, 2021, 2020]
nav: true
subtitle: My <a href="https://scholar.google.com/citations?user=tQTAiXwAAAAJ&hl=en"> Google Scholar </a> is more likely to be up to date.
---
<!-- _pages/publications.md -->
<div class="publications">

{%- for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f papers -q @*[year={{y}}]* %}
{% endfor %}

</div>