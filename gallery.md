---
layout: default
title: "Gallery"
permalink: /gallery/
---

# Gallery

<div class="gallery-grid">

  <figure class="gallery-item">
    <img src="{{ '/assets/img/gallery/HORS_10Jul2026.jpg' | relative_url }}" alt="HORS_10Jul2026">
    <figcaption> Field Survey at HORS, Hasaki Beach, Japan (10 July 2026) </figcaption>
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
