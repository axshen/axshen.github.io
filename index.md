---
layout: default
title: Home
---
### Life update

(21/11/2024)

A bi-annual update. I am currently in Malta, and have found myself with a bit of time to think about this blog again. A lot has changed in the last half-year and I feel like a lot will change in the near future as well while I try figure a few things out. The main highlights that aren't blog posts yet:

* Kev and Em got married and had the most beautiful three-day celebration
* Eddie came to visit Perth for a month
* Family from China and Melbourne came to visit for a week
* and various gigs, movie nights, and small trips down south in between the big ones.

Life is still good.

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