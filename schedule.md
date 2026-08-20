---
layout: default
title: Schedule
permalink: /schedule/
---

Tentative — dates and topics are subject to change. "Out" / "Due" refer to
when that week's assignment is posted or due; see [Assignments]({{ '/assignments/' | relative_url }})
for details.

<table>
  <thead>
    <tr>
      <th>Week</th>
      <th>Dates</th>
      <th>Topic</th>
      <th>Materials</th>
      <th>Type</th>
      <th>HW</th>
      <th>Out</th>
      <th>Due</th>
    </tr>
  </thead>
  <tbody>
    {% for week in site.data.schedule %}
    <tr>
      <td>{{ week.week }}</td>
      <td>{{ week.dates }}</td>
      <td>{{ week.topic }}</td>
      <td>
        {% for m in week.materials %}
          <div class="material-row"><a href="{{ '/assets/files/' | append: m.file | uri_escape | relative_url }}">{{ m.title }}</a></div>
        {% endfor %}
      </td>
      <td>
        {% for m in week.materials %}
          <div class="material-row"><span class="tag type-{{ m.type }}">{{ m.type }}</span></div>
        {% endfor %}
      </td>
      <td>{{ week.hw }}</td>
      <td>{{ week.hw_out }}</td>
      <td>{{ week.hw_due }}</td>
    </tr>
    {% endfor %}
  </tbody>
</table>
