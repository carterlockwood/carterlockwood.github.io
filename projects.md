---
layout: page
title: Projects
permalink: /projects/
---

Coming soon! This page will feature posts on a few of the data science projects I have worked on through school and personal endeavors. 

{% for post in site.categories.projects %}
 <li><span>{{ post.date | date_to_string }}</span> &nbsp; <a href="{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}