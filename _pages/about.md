---
title: "About"
layout: gridlay
sitemap: false
permalink: /about/
---

## Wang Lab @ CHOP

<div class="callout callout-success" markdown="0">
<div class="callout-title"><i class="fa-solid fa-microscope callout-icon"></i> Openning in Jan 2027</div>
<p>The lab will open at the Children's Hospital of Philadelphia and the University of Pennsylvania. We welcome inquiries from prospective postdoctoral researchers, PhD students, and research technicians.</p>
</div>

<div class="profile-card about-lab-card">
<div class="about-lab-logo" aria-label="Lab logo placeholder">
<span>W</span>
</div>
<div class="about-lab-copy">
<h3 class="profile-name">About the Lab</h3>
<p class="profile-summary">The Wang Lab investigates the molecular and cellular mechanisms that regulate heart development, maturation, disease, and regeneration. We integrate chromatin biology, single-cell and spatial genomics, stem-cell models, and in vivo functional genomics to connect human genetic discoveries with mechanistic cardiovascular biology.</p>
</div>
</div>

<div class="section-card">
<h3>Institutional Environment</h3>
<p>The laboratory will be affiliated with the Children’s Hospital of Philadelphia, the University of Pennsylvania, and the Cardiovascular Institute. This environment provides strong connections across pediatric cardiology, human genetics, developmental biology, stem-cell biology, genomics, bioengineering, computational biology, and translational medicine.</p>
</div>

{% if site.data.awards %}
<div class="section-card">
<h3>Focus Areas</h3>
<ul>
{% for award in site.data.awards %}
<li>{{ award.name | replace: "-","&#8211;" }}</li>
{% endfor %}
</ul>
</div>
{% endif %}

{% if site.data.funders %}
<div class="section-card">
<h3>Sponsors</h3>
<div class="sponsor-logos" style="display: flex; flex-wrap: wrap; align-items: center; justify-content: center; gap: var(--space-6);">
{% for funder in site.data.funders %}
<a href="{{ funder.url }}" target="_blank" rel="noopener noreferrer"><img src="{{ site.url }}{{ site.baseurl }}/images/{{ funder.image }}" alt="{{ funder.name | default: 'Funder' }} logo" style="max-height: 80px; max-width: 220px; border-radius: 0;" loading="lazy"></a>
{% endfor %}
</div>
</div>
{% endif %}
