---
layout: default
title: Home
---
### Life update

(29/05/2023)

Lots of travel over the last month and a half, so lots of new photos to share! Started with a trip with Jerry to Balkans and Greece, then made my way back to Helsinki by bus through Slovenia, Germany, Austria, Hungary, Poland, and the Baltics. Alps with Ruby and Budapest with Kitty along the way. Now back in Helsinki, had a chill time at Mökki, just relaxing for the rest of the month.

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