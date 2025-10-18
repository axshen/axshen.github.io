---
layout: default
title: Home
---
### Life update

(18/10/2025)

Summer is on its way back and I think it will be a good one :) Lots of fun things to share in the last few months

* First trip to the great white north!
* Ironman training in full swing, less than 2 months to go before the big race
* Eddie is back in Perth and we've all been having a blast
* A new camera to play with (film), see below a snippet from trips with our boy back

<div class='gallery' style='align-items: center'>
  <img src='https://www.dropbox.com/scl/fi/ivevsogz5kv0iypejlx04/F1340036.JPG?rlkey=jvg53oigk1ikwm8hm1ktyguyy&raw=1'>
  <img src='https://www.dropbox.com/scl/fi/0umo3k3wgqis49qug95as/F1340033.JPG?rlkey=7wzjokjuolmdif1z7pj88455d&raw=1'>
  <img src='https://www.dropbox.com/scl/fi/rm8eqgcisnb0y6sbiy65t/F1340031.JPG?rlkey=60ty3fxzic6ofxnczgnizls6l&raw=1'>
</div>

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
