---
layout: default
title: Home
---
### Life update

(15/04/2024)

Back home in Perth, and back into the swing of things. Picked up soccer again this season at SPUFC, picked up swimming with the local masters club and have settled into the work routine. Life is good. 

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