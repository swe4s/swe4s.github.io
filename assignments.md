---
layout: default
title: Assignments
permalink: /assignments/
---

All assignments and grading are through GitHub. We will post a link to each
assignment — go to the link, accept the assignment, and clone the
repository. All assignments must adhere to Python best practices and use the
proper GitHub workflow. Unless directed otherwise, only the `v1.0` release is
considered, and the date of that release is the submit time.

- **Late assignments will not be considered.**
- **Assignments without the correct release will not be considered.**
- You may work together, but original contributions are expected from every student.
- In most cases, assignments are due at 5 PM one week after they are posted.

## Weekly assignments

<table>
  <thead>
    <tr>
      <th>Assignment</th>
      <th>Out</th>
      <th>Due</th>
    </tr>
  </thead>
  <tbody>
    {% for a in site.data.assignments %}
    <tr>
      <td>{{ a.title }}</td>
      <td><span class="tag">{{ a.out }}</span></td>
      <td><span class="tag due">{{ a.due }}</span></td>
    </tr>
    {% endfor %}
  </tbody>
</table>

## Project milestones

See the [Syllabus]({{ '/' | relative_url }}#project) for full
project requirements.

| Milestone | Date |
|---|---|
| Pitch | Sep 8, 10 |
| Code review — team pairings announced | Oct 29 |
| Code review — request sent by reviewee | Nov 3 |
| Code review — returned by reviewer to reviewee | Nov 17 |
| Code review — presented by reviewer | Nov 17, 19 |
| Final presentation | Dec 1, 3 |
