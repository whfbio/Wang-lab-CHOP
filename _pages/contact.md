---
title: "Contact"
layout: gridlay
sitemap: false
permalink: /contact/
---

<header class="editorial-page-header" markdown="0">
<h1>Contact</h1>
<p class="editorial-page-lede">Find the Wang Lab location, email, and contact details for future lab inquiries.</p>
</header>

<div class="contact-grid editorial-contact-grid" markdown="0">
<div class="contact-map-card">
<iframe
  title="Map to Wang Lab"
  src="https://www.google.com/maps?q={{ site.lab_address | uri_escape }}&t=k&output=embed"
  loading="lazy"
  referrerpolicy="no-referrer-when-downgrade">
</iframe>
</div>

<div class="editorial-panel contact-info-card">
<h2 class="editorial-section-heading">§ Wang Lab @ CHOP</h2>
<div class="contact-info-list">
<div class="contact-info-item">
<i class="fa-solid fa-location-dot"></i>
<div>
<h4>Lab Address</h4>
<p>{{ site.lab_address }}</p>
<a href="https://www.google.com/maps/search/?api=1&query={{ site.lab_address | uri_escape }}" target="_blank" rel="noopener noreferrer">Open in Google Maps</a>
</div>
</div>

<div class="contact-info-item">
<i class="fa-solid fa-envelope"></i>
<div>
<h4>Email</h4>
<p><a href="mailto:{{ site.email }}">{{ site.email }}</a></p>
</div>
</div>

<div class="contact-info-item">
<i class="fa-solid fa-phone"></i>
<div>
<h4>Lab Phone</h4>
<p>{{ site.lab_phone }}</p>
</div>
</div>
</div>
</div>
</div>
