---
layout: page
title: "Blog"
permalink: /blog/
---

📝 Welcome to my blog! Here are my recent posts:

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      <span style="font-size: 0.8em; color: #888;">({{ post.date | date: "%Y-%m-%d" }})</span>
    </li>
  {% endfor %}
</ul>
