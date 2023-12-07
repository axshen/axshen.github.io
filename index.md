---
layout: default
title: Home
---
### Life update

(05/12/2023)

Almost home! Finished up travelling through Europe some number of months ago now, flew to China to be with family, solo travelled through other parts of China/HK, and now in Singapore which is my last stop before flying back to Perth.

我也在学中文。开始会写一点给我亲戚读！

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