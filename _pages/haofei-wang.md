---
title: "Haofei Wang"
layout: gridlay
sitemap: false
permalink: /haofei-wang/
---

## Haofei Wang

<div class="section-card">
<div class="pi-card">
<img src="{{ site.url }}{{ site.baseurl }}/images/{{ site.photo }}" class="pi-photo" alt="Haofei Wang" loading="lazy">
<div>
<h3 class="pi-name">Haofei Wang</h3>
<p style="font-style: italic; color: var(--text-secondary);">Principal Investigator, {{ site.institution }}</p>
<div class="pi-links">
{% if site.email %}<a href="mailto:{{ site.email }}" class="icon-link" title="Email"><i class="fa-solid fa-envelope"></i></a>{% endif %}
{% if site.links.cv and site.links.cv != "" %}<a href="{{ site.url }}{{ site.baseurl }}/{{ site.links.cv }}" class="icon-link" title="CV"><i class="ai ai-cv"></i></a>{% endif %}
{% if site.links.google_scholar and site.links.google_scholar != "" %}<a href="{{ site.links.google_scholar }}" target="_blank" rel="noopener noreferrer" class="icon-link" title="Google Scholar"><i class="ai ai-google-scholar"></i></a>{% endif %}
{% if site.links.github and site.links.github != "" %}<a href="{{ site.links.github }}" target="_blank" rel="noopener noreferrer" class="icon-link" title="GitHub"><i class="fa-brands fa-github"></i></a>{% endif %}
{% if site.links.researchgate and site.links.researchgate != "" %}<a href="{{ site.links.researchgate }}" target="_blank" rel="noopener noreferrer" class="icon-link" title="ResearchGate"><i class="ai ai-researchgate"></i></a>{% endif %}
{% if site.links.linkedin and site.links.linkedin != "" %}<a href="{{ site.links.linkedin }}" target="_blank" rel="noopener noreferrer" class="icon-link" title="LinkedIn"><i class="fa-brands fa-linkedin"></i></a>{% endif %}
{% if site.links.twitter and site.links.twitter != "" %}<a href="{{ site.links.twitter }}" target="_blank" rel="noopener noreferrer" class="icon-link" title="X"><i class="fa-brands fa-x-twitter"></i></a>{% endif %}
</div>
</div>
</div>
</div>

<div class="section-card">
<h3>Training and Appointments</h3>
{% if site.data.pi[0].education %}
<ul>
{% for education in site.data.pi[0].education %}
<li>{{ education | replace: "-","&#8211;" }}</li>
{% endfor %}
</ul>
{% endif %}
</div>

{% if site.data.awards %}
<div class="section-card">
<h3>Research Focus</h3>
<ul>
{% for award in site.data.awards %}
<li>{{ award.name | replace: "-","&#8211;" }}</li>
{% endfor %}
</ul>
</div>
{% endif %}

<div class="section-card">
<h3>Scholarly Profiles</h3>
<p>
{% if site.links.google_scholar and site.links.google_scholar != "" %}<a href="{{ site.links.google_scholar }}" target="_blank" rel="noopener noreferrer">Google Scholar</a>{% endif %}
{% if site.links.linkedin and site.links.linkedin != "" %}<br><a href="{{ site.links.linkedin }}" target="_blank" rel="noopener noreferrer">LinkedIn</a>{% endif %}
{% if site.links.twitter and site.links.twitter != "" %}<br><a href="{{ site.links.twitter }}" target="_blank" rel="noopener noreferrer">X / Twitter</a>{% endif %}
{% if site.email %}<br><a href="mailto:{{ site.email }}">{{ site.email }}</a>{% endif %}
</p>
</div>
