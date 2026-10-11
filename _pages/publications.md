---
layout: editorial
title: "Publications"
permalink: /publications/
---

<div class="shell publications-page">
  <header class="page-intro">
    <p class="section-kicker">Research / Bibliography</p>
    <h1>Publications</h1>
    <p><em>Check my <a class="text-link" href="{{ site.author.googlescholar | escape }}">Google Scholar</a> for the recent updates and details!</em></p>
  </header>
  {% assign categories = 'Preprint,Conference,Journal,Workshop' | split: ',' %}
  {% for category in categories %}
    {% assign items = site.data.publications | where: 'category', category %}
    <section aria-labelledby="category-{{ category | downcase }}">
      <div class="category-heading"><h2 id="category-{{ category | downcase }}">{{ category }}</h2><span>{{ items.size | prepend: '0' | slice: -2, 2 }}</span></div>
      <div class="publication-list">
        {% for publication in items %}{% include editorial-publication.html publication=publication %}{% endfor %}
      </div>
    </section>
  {% endfor %}
  <div class="contribution-notes">
    <p><em>'*' Denotes 'Equal Contribution/ Guidance'</em></p>
    <p><em>'^' Denotes 'Signifiant Contribution'</em></p>
  </div>
</div>
