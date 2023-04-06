---
layout: default
title: Categories
---
# Categories

<div class='gallery'>
  {% for category in site.categories %}
    <a style='color: black; text-decoration: none;' href='{{ category.url }}'>
      <img src='{{ category.image }}'>
      <h2>{{ category.title }}</h2>
    </a>
  {% endfor %}
</div>