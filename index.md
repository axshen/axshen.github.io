---
layout: default
title: Home
---
### Life update

(06/04/2023)

I've updated the style of this blog to focus more on the photos I take rather than the text that I write. Currently in Helsinki, Finland enjoying some relaxing time with Ruby before heading to the Balkans (Greece, Montenegro, Croatia) with Jerry. Still working through migrating old posts so they will show up quietly.

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