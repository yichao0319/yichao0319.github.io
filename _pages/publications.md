---
layout: page
title: Publications
rank: 20
permalink: /publications/
description: 
years: [2023,2022,2021,2020,2019,2018,2017,2016,2015,2014,2013,2011,2010,2009,2008,2007,2006,2005,2004]
nav: true
---

<div class="publications">

{% for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f conf -q @*[year={{y}}]* %}
  {% bibliography -f journal -q @*[year={{y}}]* %}
  {% bibliography -f poster -q @*[year={{y}}]* %}

{% endfor %}

</div>


