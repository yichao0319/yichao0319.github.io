---
layout: page
title: Teaching
rank: 40
permalink: /courses/
description: 
nav: true
---

<div class="news">
  {% if site.courses != blank -%} 
    <h2 class="category">Current Courses</h2>
    <div class="table-responsive">
      <table class="table table-sm table-borderless">
      {%- assign courses = site.courses | where: "status", "open" | sort: "order" -%}
      {% for item in courses -%} 
        <tr align="left">
          <th scope="row"><h6><label class="badge">Since {{ item.start_date }}</label></h6></th>
          <td>
            <h5> {{ item.name }} </h5>
            🏫  {{ item.university }} <br>
            📚  {% for id in item.course_id -%} 
                  {% if forloop.last -%}
                    {{ id }}
                  {%- else -%}
                    {{ id }}, 
                  {%- endif %}
                {%- endfor %} <br>
            🧑‍🎓  {{ item.audience }} <br>
          </td>
        </tr>
      {%- endfor %} 
      </table>
    </div>
    <!-- ----------------Past Courses---------------- -->
    <h2 class="category">Past Courses</h2>
    <div class="table-responsive">
      <table class="table table-sm table-borderless">
      {%- assign courses = site.courses | where: "status", "close" | reverse -%}
      {% for item in courses -%} 
        <tr align="left">
          <th scope="row">
            <h6><label class="badge">
              {{ item.start_date }}
            {% if item.end_date %}
               ~ {{ item.end_date }}
            {% endif %}
            </label></h6>
          </th>
          <td>
            <h5> {{ item.name }} </h5>
            🏫  {{ item.university }} <br>
            📚  {% for id in item.course_id %} 
                  {% if forloop.last %}
                    {{ id }}
                  {% else %}
                    {{ id }}, 
                  {% endif %}
                {% endfor %} <br>
            🧑‍🎓  {{ item.audience }} <br>
          </td>
        </tr>
      {%- endfor %} 
      </table>
    </div>
  {%- else -%} 
    <p>No courses provided...</p>
  {%- endif %} 
</div>


