---
title: "Haofei Wang"
layout: gridlay
sitemap: false
permalink: /haofei-wang/
---

<section class="cv-index" aria-labelledby="cv-index-title" markdown="0">
<header class="editorial-page-header cv-page-header">
<h1 id="cv-index-title">Haofei Wang</h1>
<p class="editorial-page-lede">Principal Investigator, {{ site.institution }}.</p>
</header>

<div class="cv-profile-row">
<img src="{{ site.url }}{{ site.baseurl }}/images/{{ site.photo }}" class="cv-profile-photo" alt="Haofei Wang" loading="lazy">
<div class="cv-profile-body">
<h2>Principal Investigator</h2>
<p>{{ site.title }} · {{ site.institution }}</p>
<div class="cv-profile-links">
{% if site.email %}<a href="mailto:{{ site.email }}">Email</a>{% endif %}
{% if site.links.cv and site.links.cv != "" %}<a href="{{ site.url }}{{ site.baseurl }}/{{ site.links.cv }}">CV</a>{% endif %}
{% if site.links.google_scholar and site.links.google_scholar != "" %}<a href="{{ site.links.google_scholar }}" target="_blank" rel="noopener noreferrer">Google Scholar</a>{% endif %}
{% if site.links.linkedin and site.links.linkedin != "" %}<a href="{{ site.links.linkedin }}" target="_blank" rel="noopener noreferrer">LinkedIn</a>{% endif %}
{% if site.links.twitter and site.links.twitter != "" %}<a href="{{ site.links.twitter }}" target="_blank" rel="noopener noreferrer">X / Twitter</a>{% endif %}
</div>
</div>
</div>

{% if site.data.pi[0].education %}
<h2 class="publication-section-heading">§ Training and Appointments</h2>
<div class="cv-list-row">
<div class="cv-row-meta">2027-</div>
<div class="cv-row-body">
<h3>Assistant Professor, Children's Hospital of Philadelphia and University of Pennsylvania</h3>
</div>
</div>
<div class="cv-list-row">
<div class="cv-row-meta">2023-2026</div>
<div class="cv-row-body">
<h3>{{ site.data.pi[0].education[0] | replace: "-","&#8211;" }}</h3>
</div>
</div>
<div class="cv-list-row">
<div class="cv-row-meta">2019-2023</div>
<div class="cv-row-body">
<h3>{{ site.data.pi[0].education[1] | replace: "-","&#8211;" }}</h3>
</div>
</div>
<div class="cv-list-row">
<div class="cv-row-meta">2018-2019</div>
<div class="cv-row-body">
<h3>{{ site.data.pi[0].education[2] | replace: "-","&#8211;" }}</h3>
</div>
</div>
<div class="cv-list-row">
<div class="cv-row-meta">2013-2018</div>
<div class="cv-row-body">
<h3>{{ site.data.pi[0].education[3] | replace: "-","&#8211;" }}</h3>
</div>
</div>
<div class="cv-list-row">
<div class="cv-row-meta">2009-2013</div>
<div class="cv-row-body">
<h3>{{ site.data.pi[0].education[4] | replace: "-","&#8211;" }}</h3>
</div>
</div>
{% endif %}

{% if site.data.awards %}
<h2 class="publication-section-heading">§ Research Focus</h2>
{% for award in site.data.awards %}
<div class="cv-list-row">
<div class="cv-row-meta">{{ forloop.index | prepend: "0" | slice: -2, 2 }}</div>
<div class="cv-row-body">
<h3>{{ award.name | replace: "-","&#8211;" }}</h3>
</div>
</div>
{% endfor %}
{% endif %}

<h2 class="publication-section-heading">§ Scholarly Profiles</h2>
{% if site.links.google_scholar and site.links.google_scholar != "" %}
<div class="cv-list-row">
<div class="cv-row-meta">Web</div>
<div class="cv-row-body">
<h3><a href="{{ site.links.google_scholar }}" target="_blank" rel="noopener noreferrer">Google Scholar</a></h3>
</div>
</div>
{% endif %}
{% if site.links.linkedin and site.links.linkedin != "" %}
<div class="cv-list-row">
<div class="cv-row-meta">Web</div>
<div class="cv-row-body">
<h3><a href="{{ site.links.linkedin }}" target="_blank" rel="noopener noreferrer">LinkedIn</a></h3>
</div>
</div>
{% endif %}
{% if site.links.twitter and site.links.twitter != "" %}
<div class="cv-list-row">
<div class="cv-row-meta">Web</div>
<div class="cv-row-body">
<h3><a href="{{ site.links.twitter }}" target="_blank" rel="noopener noreferrer">X / Twitter</a></h3>
</div>
</div>
{% endif %}
{% if site.email %}
<div class="cv-list-row">
<div class="cv-row-meta">Email</div>
<div class="cv-row-body">
<h3><a href="mailto:{{ site.email }}">{{ site.email }}</a></h3>
</div>
</div>
{% endif %}
</section>
