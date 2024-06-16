---
layout: secret_post
title: Internal
rank: 80
permalink: /internal/
description: 
nav: true
display_categories: [Meetings]
---

<div class="internal">
  {% if site.internal != blank -%} 
    <h2 class="category">Meetings</h2>
    <div class="table-responsive">
      <table class="table table-sm table-borderless">
      {%- assign meetings = site.internal | sort: "date" | reverse -%}
      {% for item in meetings -%} 
        <tr align="left">
          <th scope="row"><h6><label class="badge">{{ item.date  | date: "%Y %b %d" }}</label></h6></th>
          <td>
            {{ item.content }}
          </td>
        </tr>
      {%- endfor %} 
      </table>
    </div>
  {%- else -%} 
    <p>No data provided...</p>
  {%- endif %} 
</div>
