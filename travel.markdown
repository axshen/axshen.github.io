---
title: travel
layout: page
---

Some posts (and probably mainly lots of photos) of the cool places I've been to.

## posts

{% for post in site.categories.travel %}
 <li><span>{{ post.date | date_to_string }}</span> &nbsp; <a href="{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}