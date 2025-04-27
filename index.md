---
layout: default
title: Home
---
### Life update

(27/04/2025)

It's getting cold again in Perth! Went for a ride this morning and damn my fingers felt it. I've just returned from a 3 week trip over to the East coast and honestly very glad to be home. Excited to settle back into the nice routine that I had before, and to sleep in my own bed. 30 is already here apparently :)

* Kitty has just come to visited for Olivia's wedding!
* Half ironman training is still going, but has been slow with the recent holiday and mild ankle injury from soccer
* Australia's East Coast plans still in the works (check!)
* Looking forward to seeing a few more friends come back and visit Perth soon

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
