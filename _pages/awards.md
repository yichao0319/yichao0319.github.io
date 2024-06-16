---
layout: page
title: Awards
rank: 70
permalink: /awards/
description: 
nav: true
horizontal: false
---


<div class="news">
  {% if site.awards != blank -%} 
    <div class="table-responsive">
      <table class="table table-sm table-borderless">
      {%- assign awards = site.awards | reverse -%}
      {% for item in awards %} 
        <tr>
          <th scope="row"><h6><label class="badge">{{ item.date | date: "%Y %b" }}</label></h6></th>
          <td>
            {{ item.content }}
          </td>
        </tr>
      {%- endfor %} 
      </table>
    </div>
  {%- else -%} 
    <p>No awards provided...</p>
  {%- endif %} 
</div>
