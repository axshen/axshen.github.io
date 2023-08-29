---
layout: default
title: Home
---
### Life update

(29/08/2023)

A short break in Europe travel for Ruby's cousin's wedding in Indonesia. Was so lucky the last month to have mum to travel with through Italy and France, as well as my favourite aunt and her mum (ima). Finally a moment to catch up on messages, misc life stuff, and to catch up with friends and family (via videocalls) while I plan the rest of the year. Feels like I'm on the tail end of the gap year now with the last holidays in Europe, and my return trip to Asia, all organised.

Trips to come: Spain and Portugal with Taf, Mel and Tim, with the siblings in Germany and the Netherlands, and a short stint back in Helsinki before travelling together to China with the rest of the family!

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