---
title: tech
layout: page
---

A space for me to share science/engineering/technology related interests.

## posts

{% for post in site.categories.tech %}
 <li><span>{{ post.date | date_to_string }}</span> &nbsp; <a href="{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}