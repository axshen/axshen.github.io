---
layout: default
title: Blog
---

# Blog

<ul>
  {% for post in site.posts %}
    <li>
      <p><a href="{{ post.url }}">{{ post.title }}</a></p>
    </li>
  {% endfor %}
</ul>