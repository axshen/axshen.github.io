---
layout: default
title: Home
---
### Life update

(03/03/2025)

We're coming to the end now already of another amazing and full summer. Lots of time ourdoors (though frankly not enough time at the beach), some new hobbies, and new important people in my life. Feeling pretty good about things right now, curious about how the rest of the year will play out. It seems to be filling out already with some big rocks!

* Still training for a half-ironman (though I've decided to take it easier)
* The big Americas trip has been postponed, with poor Jerry's recent major injury. We'll do something smaller instead!
* Australia's East Coast plans still in the works
* 30 (coming in hot...)

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
