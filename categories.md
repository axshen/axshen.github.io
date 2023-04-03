---
layout: default
title: Categories
---
<h1>Categories</h1>

<ul>
  {% for category in site.categories %}
    <li>
      <h3><a href="{{  category.url }}">{{  category.title }}</a></h3>
      <p>{{ category.content | markdownify }}</p>
    </li>
  {% endfor %}
</ul>