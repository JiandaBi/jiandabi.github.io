---
layout: page
permalink: /gallery/
title: Gallery
nav: true
nav_order: 5
description: a selection of photos I took during my travels!
---

<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/baguettebox.js@1.12.0/dist/baguetteBox.min.css">

<style>
.gallery-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(240px, 1fr));
  gap: 1rem;
}
.gallery-grid a {
  display: block;
  overflow: hidden;
  border-radius: 4px;
}
.gallery-grid img {
  width: 100%;
  height: 200px;
  object-fit: cover;
  transition: transform 0.3s ease;
  display: block;
}
.gallery-grid a:hover img {
  transform: scale(1.05);
}
</style>

<div class="gallery-grid" id="gallery">

<a href="/assets/img/gallery/01.jpg"><img alt="" src="/assets/img/gallery/01.jpg"></a>
<a href="/assets/img/gallery/02.jpg"><img alt="" src="/assets/img/gallery/02.jpg"></a>
<a href="/assets/img/gallery/03.jpg"><img alt="" src="/assets/img/gallery/03.jpg"></a>
<a href="/assets/img/gallery/04.jpg"><img alt="" src="/assets/img/gallery/04.jpg"></a>
<a href="/assets/img/gallery/05.jpg"><img alt="" src="/assets/img/gallery/05.jpg"></a>
<a href="/assets/img/gallery/06.jpg"><img alt="" src="/assets/img/gallery/06.jpg"></a>
<a href="/assets/img/gallery/07.jpg"><img alt="" src="/assets/img/gallery/07.jpg"></a>
<a href="/assets/img/gallery/08.jpg"><img alt="" src="/assets/img/gallery/08.jpg"></a>
<a href="/assets/img/gallery/09.jpg"><img alt="" src="/assets/img/gallery/09.jpg"></a>

</div>

<script src="https://cdn.jsdelivr.net/npm/baguettebox.js@1.12.0/dist/baguetteBox.min.js"></script>
<script>
window.addEventListener('load', function() {
  baguetteBox.run('#gallery', {
    animation: 'fadeIn',
    noScrollbars: true,
  });
});
</script>
