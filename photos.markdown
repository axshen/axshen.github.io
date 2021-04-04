---
title: photos
layout: page
---

A collection of moments captured.

## posts

{% for post in site.categories.photos %}
 <li><span>{{ post.date | date_to_string }}</span> &nbsp; <a href="{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}