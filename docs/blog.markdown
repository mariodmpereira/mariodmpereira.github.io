---
layout: page
title: Blog
permalink: /blog/
nav_exclude: true
---

# Blog
<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }} - {{ post.date | date: '%B %d, %Y' }}</a>
    </li>
  {% endfor %}
</ul>