---
layout: default
title: thomasstep.com
show_mailchimp_signup: true
---

<p style="text-align: center;font-size:25px"><b>Creatives</b></p>



{% for post in site.posts %}
  <p><a href="{{ post.url }}">{{ post.title }}</a> <br> {{ post.date | date: "%-d %B %Y" }}</p>
  {% assign tcategories = post.tags | join:'|' | append:'|' %}
  {% assign rawcategories = rawcategories | append:tcategories %}
{% endfor %}