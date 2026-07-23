---
title: "Team"
layout: gridlay
sitemap: false
permalink: /team/
---

<header class="editorial-page-header" markdown="0">
<h1>Team</h1>
<p class="editorial-page-lede">Meet the people building the Wang Lab and the open roles for researchers who want to join.</p>
</header>

<div class="editorial-note" markdown="0">
<div class="editorial-note-title"><i class="fa-solid fa-user-plus"></i> Recruiting</div>
<p>We are recruiting postdoctoral researchers, PhD students, and research technicians.</p>
</div>

<section class="editorial-section">
<h2 class="editorial-section-heading">§ Principal Investigator</h2>

<div class="editorial-panel">
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
</section>

{% if site.data.team_members.size > 0 %}
<section class="editorial-section">
<h2 class="editorial-section-heading">§ Open Roles</h2>

<div class="team-grid" markdown="0">
{% for member in site.data.team_members %}
<div class="team-card">
<img src="{{ "/images/" | append: member.photo | relative_url }}" class="team-photo" alt="{{ member.name }}" loading="lazy">
<h4 class="team-name">{{ member.name }}</h4>
<p class="team-info">{{ member.info }}</p>
{% if member.url %}
<a href="{{ member.url | relative_url }}" class="btn-pill btn-website team-role-button">Learn more details</a>
{% endif %}
</div>
{% endfor %}
</div>
</section>
{% endif %}
