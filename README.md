# swe4s.github.io

Course website for **Software Engineering for Scientists**, built with
[Jekyll](https://jekyllrb.com/) and hosted on GitHub Pages.

## Local development

```
gem install jekyll bundler
jekyll serve
```

Then open http://localhost:4000.

## Editing content

- `_config.yml` — site title, description, semester, nav links
- `syllabus.md` — edit directly
- `_data/schedule.yml` — weekly schedule (rendered on the Schedule page)
- `_data/assignments.yml` — labs/homework (rendered on the Assignments page)
- `_data/staff.yml` — instructor/TA info (rendered on the Staff page)

Pushing to `main` automatically rebuilds and deploys the site via GitHub
Pages.
