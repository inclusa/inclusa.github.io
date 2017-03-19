---
layout: page
permalink: /productivitat/
title: pro
description: Productivitat
---

<ul class="post-list">
{% for article in site.productivity reversed %}
    <li>
        <h2><a class="poem-title" href="{{ article.url | prepend: site.baseurl }}">{{ article.title }}</a></h2>
        <p class="post-meta">{{ article.date | date: '%B %-d, %Y — %H:%M' }}</p>
      </li>
{% endfor %}
</ul>
