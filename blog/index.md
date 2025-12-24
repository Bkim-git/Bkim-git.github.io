---
layout: default
title: "Blog"
---
## 📝 Welcome to My Blog

---

<div style="display: flex; flex-direction: column; gap: 20px;">

  {% for post in site.posts %}
    <div style="padding: 16px; border: 1px solid #ddd; border-radius: 8px; box-shadow: 0 2px 4px rgba(0,0,0,0.05);">
      <h3 style="margin-top: 0; margin-bottom: 6px;">
        <a href="{{ post.url | relative_url }}" style="text-decoration: none; color: #007acc;">
          {{ post.title }}
        </a>
      </h3>
      <p style="font-size: 0.85em; color: #666; margin-bottom: 0.8em;">
        📅 {{ post.date | date: "%Y-%m-%d" }}
      </p>
      {% if post.excerpt %}
        <p style="margin: 0;">{{ post.excerpt | strip_html | truncate: 160 }}</p>
      {% else %}
        <p style="margin: 0; color: #999;">No preview available...</p>
      {% endif %}
    </div>
  {% endfor %}

</div>
