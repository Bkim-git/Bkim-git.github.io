---
layout: default
title: "Gallery"
permalink: /gallery/
albums:
  - folder: 2026-07-10_HORS-Hasaki
    title: "Fixed lidar calibration at HORS, Hasaki Beach, Japan"
    date: "10 July 2026"
    caption: ""
  - folder: 2026-04-10_Oleron
    title: "Field test with Drone-borne lidar at Oleron island, France"
    date: "10 April 2026" 
    caption: ""
---

# Gallery

{%- assign gallery_root = '/assets/img/gallery/' -%}
{%- assign image_exts = '.jpg .jpeg .png .webp .JPG .JPEG .PNG' | split: ' ' -%}

{% for album in page.albums %}
{%- assign dir = gallery_root | append: album.folder | append: '/' -%}
{%- assign photos = site.static_files | where_exp: 'f', 'f.path contains dir' | where_exp: 'f', 'image_exts contains f.extname' | sort: 'path' -%}
<div class="album">
<h2>{{ album.title }}</h2>
{%- if album.date %}
<p class="album-date">{{ album.date }}</p>
{%- endif %}
{%- if album.caption and album.caption != '' %}
<p>{{ album.caption }}</p>
{%- endif %}
{%- if photos.size > 0 %}
<div class="gallery-grid">
{%- for photo in photos %}
<a href="{{ photo.path | relative_url }}"><img src="{{ photo.path | relative_url }}" alt="{{ album.title }}" loading="lazy"></a>
{%- endfor %}
</div>
{%- else %}
<p class="album-empty">No images found in <code>assets/img/gallery/{{ album.folder }}/</code></p>
{%- endif %}
</div>
{% endfor %}

<style>
.album {
  margin-bottom: 40px;
}

.album h2 {
  margin-bottom: 4px;
}

.album-date {
  font-size: 0.85rem;
  color: #666;
  margin-bottom: 12px;
}

.album-empty {
  font-size: 0.85rem;
  color: #999;
}

.gallery-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(160px, 1fr));
  gap: 12px;
}

.gallery-grid img {
  width: 100%;
  aspect-ratio: 4 / 3;
  object-fit: cover;
  border-radius: 4px;
  display: block;
}
</style>
