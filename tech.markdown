---
title: tech
layout: page
---

They call me tech bro stin. I studied physics and engineering, and have worked primarily in computing. I'm interested in so many topics in this maths / science / technology space - more than the time I have to explore and learn them. Here's a bunch of posts about the projects that I have had the time to work on, and some thoughts about the things I've learned.

## posts

{% for post in site.categories.tech %}
 <li><span>{{ post.date | date_to_string }}</span> &nbsp; <a href="{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}