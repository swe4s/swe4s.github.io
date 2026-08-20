---
layout: default
title: Staff
permalink: /staff/
---

<div class="card-grid">
  {% for person in site.data.staff %}
  <div class="card">
    <h3>{{ person.name }}</h3>
    <p>{{ person.role }}</p>
    <p>Office hours: {{ person.office_hours }}</p>
  </div>
  {% endfor %}
</div>
