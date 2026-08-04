---
layout: default
title: "Gallery"
permalink: /gallery/
albums:
  - folder: 2026-07-10_HORS-Hasaki
    title: "Fixed lidar calibration at HORS, Hasaki Beach, Japan"
    date: "10 Jul. 2026"
    caption: ""
  - folder: 2026-04-10_Oleron
    title: "Field test with Drone-borne lidar at Oleron island, France"
    date: "10 Apr. 2026"
    caption: ""
  - folder: 2026-02-25_PhD-graduation
    title: "PhD graduation ceremony at Seoul National University"
    date: "25 Feb. 2026"
    caption: ""
---

## 📷 Gallery

---

{% assign gallery_root = '/assets/img/gallery/' %}
{% assign image_exts = '.jpg .jpeg .png .webp .JPG .JPEG .PNG' | split: ' ' %}

{% for album in page.albums %}
{% assign dir = gallery_root | append: album.folder | append: '/' %}
{% assign photos = site.static_files | where_exp: 'f', 'f.path contains dir' | where_exp: 'f', 'image_exts contains f.extname' | sort: 'path' %}

<div class="album-head"><h2 class="album-title">{{ album.title }}</h2>{% if album.date %}<span class="album-date">{{ album.date }}</span>{% endif %}</div>

{% if album.caption and album.caption != '' %}
<p class="album-caption">{{ album.caption }}</p>
{% endif %}

{% if photos.size > 0 %}
<div class="album-strip">{% if photos.size > 1 %}<button type="button" class="strip-nav prev" aria-label="Scroll left" onclick="var r=this.parentNode.querySelector('.gallery-row');r.scrollBy({left:-r.clientWidth*0.8,behavior:'smooth'})">&#8249;</button>{% endif %}<div class="gallery-row">{% for photo in photos %}<img src="{{ photo.path | relative_url }}" alt="{{ album.title }}" loading="lazy">{% endfor %}</div>{% if photos.size > 1 %}<button type="button" class="strip-nav next" aria-label="Scroll right" onclick="var r=this.parentNode.querySelector('.gallery-row');r.scrollBy({left:r.clientWidth*0.8,behavior:'smooth'})">&#8250;</button>{% endif %}</div>
{% else %}
<p class="album-empty">No images found in assets/img/gallery/{{ album.folder }}/</p>
{% endif %}

{% endfor %}

<style>
.album-head {
  display: flex;
  align-items: baseline;
  justify-content: space-between;
  gap: 12px;
  margin-bottom: 8px;
}

.album-title {
  font-size: 15px;
  margin: 0;
}

.album-date {
  font-size: 12px;
  color: #666;
  white-space: nowrap;
}

.album-caption {
  margin-bottom: 12px;
}

.album-empty {
  font-size: 0.85rem;
  color: #999;
}

/* Single row; the scrollbar is hidden and replaced by the arrow buttons. */
.album-strip {
  position: relative;
  margin-bottom: 40px;
}

.gallery-row {
  display: flex;
  gap: 12px;
  overflow-x: auto;
  scrollbar-width: none;
  -ms-overflow-style: none;
}

.gallery-row::-webkit-scrollbar {
  display: none;
}

.gallery-row img {
  flex: 0 0 auto;
  height: 150px;
  width: auto;
  max-width: none;
  border-radius: 4px;
  display: block;
}

.strip-nav {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  z-index: 1;
  width: 28px;
  height: 28px;
  padding: 0;
  border: 0;
  border-radius: 50%;
  background: rgba(0, 0, 0, 0.45);
  color: #fff;
  font-size: 18px;
  line-height: 1;
  cursor: pointer;
}

.strip-nav:hover {
  background: rgba(0, 0, 0, 0.75);
}

.strip-nav.prev {
  left: 6px;
}

.strip-nav.next {
  right: 6px;
}
</style>
