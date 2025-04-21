---
layout: default
title: "Blog"
permalink: /blog/
---


📝 Welcome to my blog. Here are the latest posts:

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url | relative_url }}">{{ 250421-post }}</a>
      <span style="font-size: 0.8em; color: #888;">({{ post.date | date: "%Y-%m-%d" }})</span>
    </li>
  {% endfor %}
</ul>
