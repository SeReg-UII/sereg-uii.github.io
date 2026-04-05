---
layout: page
title: Gallery
permalink: /gallery/
description: Photos from our events, conferences, and lab life.
nav_order: 4
---

<div class="row g-3">

  {% for photo in site.data.gallery %}
  <div class="col-6 col-md-4 col-lg-3">
    <div class="gallery-item">
      <a href="{{ photo.image | relative_url }}" data-bs-toggle="modal" data-bs-target="#galleryModal"
         data-img="{{ photo.image | relative_url }}" data-caption="{{ photo.caption }}">
        <img src="{{ photo.image | relative_url }}" alt="{{ photo.caption }}"
             class="img-fluid gallery-thumb rounded shadow-sm" />
      </a>
      {% if photo.caption %}
      <p class="gallery-caption text-muted small text-center mt-1">{{ photo.caption }}</p>
      {% endif %}
    </div>
  </div>
  {% endfor %}

  {% if site.data.gallery.size == 0 %}
  <!-- Placeholder grid when no photos are added yet -->
  {% for i in (1..8) %}
  <div class="col-6 col-md-4 col-lg-3">
    <div class="gallery-placeholder rounded d-flex align-items-center justify-content-center bg-light shadow-sm">
      <i class="fas fa-image fa-2x text-muted"></i>
    </div>
    <p class="gallery-caption text-muted small text-center mt-1">Photo {{ i }}</p>
  </div>
  {% endfor %}
  {% endif %}

</div>

<!-- Lightbox Modal -->
<div class="modal fade" id="galleryModal" tabindex="-1" aria-hidden="true">
  <div class="modal-dialog modal-lg modal-dialog-centered">
    <div class="modal-content bg-transparent border-0">
      <div class="modal-body p-0 text-center">
        <img src="" id="galleryModalImg" class="img-fluid rounded shadow" alt="" />
        <p id="galleryModalCaption" class="text-white mt-2 mb-0"></p>
      </div>
    </div>
  </div>
</div>

<script>
  document.querySelectorAll('[data-bs-target="#galleryModal"]').forEach(function(el) {
    el.addEventListener('click', function() {
      document.getElementById('galleryModalImg').src = this.dataset.img;
      document.getElementById('galleryModalCaption').textContent = this.dataset.caption || '';
    });
  });
</script>
