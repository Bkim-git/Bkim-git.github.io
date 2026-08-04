---
layout: default
title: "Gallery"
permalink: /gallery/
albums:
  - folder: 2026-07-10_HORS-Hasaki
    title: "Field Survey at HORS, Hasaki Beach, Japan"
    date: "10 July 2026"
    caption: ""
  - folder: 2026-04-10_Oleron
    title: "Field Survey at Troja, Oleron, France"
    date: "10 July 2026"
    caption: ""
---

## 📷 Gallery

---

{% assign gallery_root = '/assets/img/gallery/' %}
{% assign image_exts = '.jpg .jpeg .png .webp .JPG .JPEG .PNG' | split: ' ' %}

{% for album in page.albums %}
{% assign dir = gallery_root | append: album.folder | append: '/' %}
{% assign photos = site.static_files | where_exp: 'f', 'f.path contains dir' | where_exp: 'f', 'image_exts contains f.extname' | sort: 'path' %}

<h2 class="album-title">{{ album.title }}</h2>

{% if album.date %}
<p class="album-date">{{ album.date }}</p>
{% endif %}

{% if album.caption and album.caption != '' %}
<p class="album-caption">{{ album.caption }}</p>
{% endif %}

{% if photos.size > 0 %}
<div class="gallery-row">{% for photo in photos %}<img src="{{ photo.path | relative_url }}" alt="{{ album.title }}" loading="lazy">{% endfor %}</div>
{% else %}
<p class="album-empty">No images found in assets/img/gallery/{{ album.folder }}/</p>
{% endif %}

{% endfor %}

<style>
.album-title {
  font-size: 18px;
  margin-bottom: 2px;
}

.album-date {
  font-size: 0.85rem;
  color: #666;
  margin-bottom: 12px;
}

.album-caption {
  margin-bottom: 12px;
}

.album-empty {
  font-size: 0.85rem;
  color: #999;
}

/* Single row, scrolls right when the album has more photos than fit. */
.gallery-row {
  display: flex;
  gap: 12px;
  overflow-x: auto;
  padding-bottom: 10px;
  margin-bottom: 40px;
}

.gallery-row img {
  flex: 0 0 auto;
  height: 150px;
  width: auto;
  max-width: none;
  border-radius: 4px;
  display: block;
}
</style>
