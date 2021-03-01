---
title: work
layout: page
---

I've done a bunch of different jobs for work so far in my career. This has included consulting, application development (mobile, web) and data science. Here's a space for me to write about all of the projects and interests concepts in that space.

## posts

{% for post in site.categories.work %}
 <li><span>{{ post.date | date_to_string }}</span> &nbsp; <a href="{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}