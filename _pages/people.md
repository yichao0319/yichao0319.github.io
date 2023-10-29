---
layout: page
title: People
rank: 5
permalink: /people/
description: 
nav: false
display_categories: [Faculty, Postdoc, PhD Student, Master Student, Undergraduate Student, Alumni]
---

<div class="projects">
  <!-- Display categorized people -->
  {%- for category in page.display_categories %}
    <h2 class="category">{{ category }}</h2>
    {%- assign categorized_people = site.people | where: "status", category -%}
    {%- assign sorted_people = categorized_people %}
    <!-- Generate cards for each person -->
    <div class="container">
      <div class="row row-cols-1">
        {%- for person in sorted_people -%}
          <!-- Generate a card for the person -->
          <div class="card-item col">
            {%- if person.redirect -%}
              <a href="{{ person.redirect }}">
            {%- else -%}
              <a href="{{ person.url | relative_url }}">
            {%- endif -%}
              <div class="card hoverable">
                <div class="row row-cols-2">
                  <div class="card-img col-md-4">
                    {%- include figure.html
                      path=person.img
                      alt="person thumbnail" -%}
                  </div>
                  <div class="card-body col-md-8">
                    <h5 class="card-title" style="line-height: 1px;">{{ person.first_name }} {{ person.last_name }}</h5>
                    <div class="card-text" style="font-size: 16px; padding-bottom: 10px;">
                      {% if person.status == "Faculty" %}
                        {{ person.occupation }} @ {{ person.affiliation }}
                      {% elsif person.status == "Alumni" %}
                        {{ person.occupation }}, {{ person.affiliation }}
                      {% else %}
                        {{ person.status }}
                      {% endif %}
                    </div>
                    <p class="card-text">{{ person.bio }}</p>
                  </div>
                </div>
              </div>
            </a>
          </div>
          <!-- END: Generate a card for the person -->
        {%- endfor %}
      </div>
    </div>
  {% endfor %}
</div>
