---
layout: default
title: Home
---
### Life update

(02/01/2025)

Happy new year! Writing this in holiday mode after a wonderful Christmas and New Years break. Just a week off to enjoy friends, family, hobbies, to go away, and to relax. A full week where time felt like it had moved slower. It has been a big year of ups and downs, but after reflecting I can say it's been net great and I feel very lucky for the life that I get to live.

Some new things to (hopefully) come this year:

* Training for a half-ironman
* The Americas
* Australia's East Coast, for how long?
* 30

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
