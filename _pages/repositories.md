---
layout: page
permalink: /repositories/
title: Repositories
nav: true
nav_order: 4
---

## GitHub

<div class="repositories d-flex flex-wrap justify-content-start">
  {% for user in site.data.repositories.github_users %}
    {% include repository/repo_user.liquid username=user %}
  {% endfor %}
</div>

---

## Selected Repositories

<div class="repositories d-flex flex-wrap justify-content-start">
  {% for repo in site.data.repositories.github_repos %}
    {% include repository/repo.liquid repository=repo %}
  {% endfor %}
</div>
