---
title: "Team"
layout: gridlay
sitemap: false
permalink: /team/
---

## Team

**We are recruiting postdoctoral researchers, PhD students, and research technicians.**

## Principal Investigator

<div class="section-card">
<div class="pi-card">
<a href="{{ site.url }}{{ site.baseurl }}/haofei-wang/" class="pi-card-photo-link" aria-label="Open Haofei Wang CV page">
<img src="{{ site.url }}{{ site.baseurl }}/images/{{ site.photo }}" class="pi-photo" alt="Haofei Wang" loading="lazy">
</a>
<div>
<h3 class="pi-name"><a href="{{ site.url }}{{ site.baseurl }}/haofei-wang/">Haofei Wang</a></h3>
<p style="font-style: italic; color: var(--text-secondary);">Principal Investigator, {{ site.institution }}</p>
<div class="pi-links">
<a href="{{ site.url }}{{ site.baseurl }}/haofei-wang/" class="icon-link" title="CV"><i class="ai ai-cv"></i></a>
{% if site.email %}<a href="mailto:{{ site.email }}" class="icon-link" title="Email"><i class="fa-solid fa-envelope"></i></a>{% endif %}
{% if site.links.google_scholar and site.links.google_scholar != "" %}<a href="{{ site.links.google_scholar }}" target="_blank" rel="noopener noreferrer" class="icon-link" title="Google Scholar"><i class="ai ai-google-scholar"></i></a>{% endif %}
{% if site.links.linkedin and site.links.linkedin != "" %}<a href="{{ site.links.linkedin }}" target="_blank" rel="noopener noreferrer" class="icon-link" title="LinkedIn"><i class="fa-brands fa-linkedin"></i></a>{% endif %}
{% if site.links.twitter and site.links.twitter != "" %}<a href="{{ site.links.twitter }}" target="_blank" rel="noopener noreferrer" class="icon-link" title="X"><i class="fa-brands fa-x-twitter"></i></a>{% endif %}
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

{% if site.data.team_members.size > 0 %}
## Open Roles

<div class="team-grid" markdown="0">
{% for member in site.data.team_members %}
<div class="team-card">
<img src="{{ site.url }}{{ site.baseurl }}/images/{{ member.photo }}" class="team-photo" alt="{{ member.name }}" loading="lazy">
<h4 class="team-name">{{ member.name }}</h4>
<p class="team-info">{{ member.info }}</p>
{% if member.url %}
<a href="{{ member.url | relative_url }}" class="btn-pill btn-website team-role-button">Learn more details</a>
{% endif %}
</div>
{% endfor %}
</div>
{% endif %}
