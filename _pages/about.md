---
title: "About"
layout: gridlay
sitemap: false
permalink: /about/
---

<header class="editorial-page-header" markdown="0">
<h1>Wang Lab @ CHOP</h1>
<p class="editorial-page-lede">The Wang Lab studies cardiovascular development, maturation, disease, and regeneration through functional genomics and single-cell biology.</p>
</header>

<div class="editorial-note editorial-note-success" markdown="0">
<div class="editorial-note-title"><i class="fa-solid fa-microscope"></i> Opening in Jan 2027</div>
<p>The lab will open at the Children's Hospital of Philadelphia and the University of Pennsylvania.</p>
</div>

<section class="editorial-section">
<h2 class="editorial-section-heading">§ About the Lab</h2>

<div class="about-lab-card editorial-panel">
<div class="about-lab-logo">
<img src="{{ "/images/logo_color.png" | relative_url }}" alt="Wang Lab logo" loading="lazy">
</div>
<div class="about-lab-copy">
<p>The Wang Lab investigates the molecular and cellular mechanisms that regulate heart development, maturation, disease, and regeneration. We integrate chromatin biology, single-cell and spatial genomics, stem-cell models, and in vivo functional genomics to connect human genetic discoveries with mechanistic cardiovascular biology.</p>
</div>
</div>
</section>

<section class="editorial-section">
<h2 class="editorial-section-heading">§ Environment</h2>
<div class="editorial-panel">
<p>The laboratory will be affiliated with the Children’s Hospital of Philadelphia, the University of Pennsylvania, and the Cardiovascular Institute. This environment provides strong connections across pediatric cardiology, human genetics, developmental biology, stem-cell biology, genomics, bioengineering, computational biology, and translational medicine.</p>
</div>
</section>

{% if site.data.awards %}
<section class="editorial-section">
<h2 class="editorial-section-heading">§ Focus Areas</h2>
<ul class="editorial-list">
{% for award in site.data.awards %}
<li>{{ award.name | replace: "-","&#8211;" }}</li>
{% endfor %}
</ul>
</section>
{% endif %}

{% if site.data.funders %}
<section class="editorial-section">
<h2 class="editorial-section-heading">§ Sponsors</h2>
<div class="editorial-panel sponsor-logos">
{% for funder in site.data.funders %}
<a href="{{ funder.url }}" target="_blank" rel="noopener noreferrer"><img src="{{ site.url }}{{ site.baseurl }}/images/{{ funder.image }}" alt="{{ funder.name | default: 'Funder' }} logo" loading="lazy"></a>
{% endfor %}
</div>
</section>
{% endif %}
