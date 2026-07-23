---
title: "Lab News"
layout: gridlay
sitemap: false
permalink: /allnews.html
---

<header class="editorial-page-header" markdown="0">
<h1>Lab News</h1>
<p class="editorial-page-lede">Updates from the Wang Lab.</p>
</header>

<section class="editorial-section" markdown="0">
<h2 class="editorial-section-heading">§ Updates</h2>
<div class="editorial-panel">
<div class="news-timeline">
{% for article in site.data.news %}
<div class="news-item">
<span class="news-date">{{ article.date }}</span>
<span class="news-headline">{{ article.headline }}</span>
</div>
{% endfor %}
</div>
</div>
</section>
