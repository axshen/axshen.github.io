---
title: misc
layout: page
---

If it doesn't fit in either other category, I'll put it here.

## posts

{% for post in site.categories.misc %}
 <li><span>{{ post.date | date_to_string }}</span> &nbsp; <a href="{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}