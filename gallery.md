---
layout: default
title: "Gallery"
permalink: /gallery/
---

# Gallery

<div class="gallery-grid">

  <figure class="gallery-item">
    <img src="{{ '/assets/img/gallery/photo1.jpg' | relative_url }}" alt="Field campaign">
    <figcaption>Field campaign at Hasaki Beach, Japan.</figcaption>
  </figure>

  <figure class="gallery-item">
    <img src="{{ '/assets/img/gallery/photo2.jpg' | relative_url }}" alt="LiDAR measurement">
    <figcaption>LiDAR measurement of surf-zone waves.</figcaption>
  </figure>

</div>

<style>
.gallery-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
  gap: 24px;
  margin-top: 20px;
}

.gallery-item {
  margin: 0;
}

.gallery-item img {
  width: 100%;
  height: auto;
  display: block;
  border-radius: 4px;
}

.gallery-item figcaption {
  margin-top: 8px;
  font-size: 0.9rem;
  line-height: 1.4;
  color: #666;
}
</style>
