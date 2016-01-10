---
layout: page
title: Posts
---

{% for post in site.categories.posts %}
  * {{ post.date | date_to_string }} &raquo; [ {{ post.title }} ]({{ post.url }})
{% endfor %}
