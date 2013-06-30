---
layout: page
title: Software Programming Blog!
tagline: Supporting tagline
---
{% include JB/setup %}


<div class="posts">
  {% for post in site.posts %}
  <span>{{ post.date | date_to_string }}</span> &raquo;<br /><b><i><a href="{{ BASE_PATH }}{{ post.url }}" style="font-size: 28px;">{{ post.title }}</a></i></b><br /><br />
<br />
  {% endfor %}
</div>



