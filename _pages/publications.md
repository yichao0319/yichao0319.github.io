---
layout: page
title: Publications
rank: 20
permalink: /publications/
description: 
years: [2026,2025,2024,2023,2022,2021,2020,2019,2018,2017,2016,2015,2014,2013,2011,2010,2009,2008,2007,2006,2005,2004]
nav: true
---

<div class="publications">

{% for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f conf --group_by none -q @*[year={{y}}]* %}
  {% bibliography -f journal --group_by none -q @*[year={{y}}]* %}
  {% bibliography -f poster --group_by none -q @*[year={{y}}]* %}
  {%- capture preprint_count -%}{% bibliography_count -f preprint -q @*[year={{y}}]* %}{%- endcapture -%}
  {%- assign preprint_count = preprint_count | plus: 0 -%}
  {% if preprint_count > 0 %}
    <h3>Preprints</h3>
    {% bibliography -f preprint --group_by none -q @*[year={{y}}]* %}
  {% endif %}

{% endfor %}

</div>

