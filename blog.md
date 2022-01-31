---
layout: default
title: Rajat Jain

---

<p style="text-align: center;font-size:25px"><b>Blog</b></p>



{% for blog in site.blog %}
  <p><a href="{{ blog.url }}">{{ blog.title }}</a> <br> {{ blog.date | date: "%-d %B %Y" }}</p>
  {% assign tcategories = blog.tags | join:'|' | append:'|' %}
  {% assign rawcategories = rawcategories | append:tcategories %}
{% endfor %}