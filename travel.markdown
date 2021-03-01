---
title: travel
layout: page
---

A record of the places I've been to outside of my home city.

## posts

{% for post in site.categories.travel %}
 <li><span>{{ post.date | date_to_string }}</span> &nbsp; <a href="{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}