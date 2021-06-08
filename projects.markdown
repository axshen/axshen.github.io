---
title: projects
layout: page
---

{% for post in site.categories.projects %}
 <h4 style="display:inline"><a href="{{ post.url }}">{{ post.title }}</a></h4>
 <h5> {{ post.date | date_to_string }} </h5>
 <p>{{ post.description }}</p>
 <br/>
{% endfor %}