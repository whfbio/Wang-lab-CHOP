---
title: "About"
layout: gridlay
sitemap: false
permalink: /about/
---

## About

<div class="section-card">
<div class="pi-card">
<img src="{{ site.url }}{{ site.baseurl }}/images/{{ site.photo }}" class="pi-photo" alt="{{ site.name }}" loading="lazy">
<div>
<h3 class="pi-name">Haofei Wang</h3>
<p style="font-style: italic; color: var(--text-secondary);">Principal Investigator, {{ site.institution }}</p>
<div class="pi-links">
{% if site.email %}<a href="mailto:{{ site.email }}" class="icon-link" title="Email"><i class="fa-solid fa-envelope"></i></a>{% endif %}
{% if site.links.cv and site.links.cv != "" %}<a href="{{ site.url }}{{ site.baseurl }}/{{ site.links.cv }}" class="icon-link" title="CV"><i class="ai ai-cv"></i></a>{% endif %}
{% if site.links.google_scholar and site.links.google_scholar != "" %}<a href="{{ site.links.google_scholar }}" target="_blank" rel="noopener noreferrer" class="icon-link" title="Google Scholar"><i class="ai ai-google-scholar"></i></a>{% endif %}
{% if site.links.github and site.links.github != "" %}<a href="{{ site.links.github }}" target="_blank" rel="noopener noreferrer" class="icon-link" title="GitHub"><i class="fa-brands fa-github"></i></a>{% endif %}
{% if site.links.researchgate and site.links.researchgate != "" %}<a href="{{ site.links.researchgate }}" target="_blank" rel="noopener noreferrer" class="icon-link" title="ResearchGate"><i class="ai ai-researchgate"></i></a>{% endif %}
</div>
{% if site.data.pi[0].education %}
<ul style="margin-top: var(--space-4);">
{% for education in site.data.pi[0].education %}
<li>{{ education | replace: "-","&#8211;" }}</li>
{% endfor %}
</ul>
{% endif %}
</div>
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
