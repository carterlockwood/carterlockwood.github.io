---
layout: page
title: Blog
permalink: /blog/
---

A place for content that doesn't necessarily fall into the 'data science' category!

{% for post in site.categories.tech %}
 <li><span>{{ post.date | date_to_string }}</span> &nbsp; <a href="{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}