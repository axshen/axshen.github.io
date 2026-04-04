---
layout: default
title: Home
---
### Life update

(04/04/2026)

Time is moving faster now and I'm getting older and have less energy. Might have trained too hard at the end of last year oops! But life is still great. Summer is already over, but it's been jam packed already

* Kelsey is living here! Visa granted, exam 1/2 passed, things looking up
* Soccer season is starting up again, still biking heaps (power stats coming soon)
* We just got back from a great holiday in China. Photos coming soon (I am so far behind on sharing things here).

### Recent posts

<div class='gallery'>
  {% for post in site.posts %}
    <a style='color: black; text-decoration: none;' href='{{ post.url }}'>
      <img src='{{ post.image }}'>
      <p>{{ post.date | date_to_string }}: {{ post.title }}</p>
    </a>
    {% if forloop.index >= 3 %}
      {% break %}
    {% endif %}
  {% endfor %}
</div>
