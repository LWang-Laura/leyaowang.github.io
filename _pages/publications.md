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
  {% assign other = site.data.publications | where_exp: 'pub', 'pub.areas == empty' %}
  {% assign groups = site.data.research_areas | map: 'key' | push: 'other' %}
  {% assign anchored = ',' %}
  {% for key in groups %}
    {% if key == 'other' %}
      {% assign items = other %}{% assign title = 'Other work' %}{% assign description = '' %}
    {% else %}
      {% assign area = site.data.research_areas | where: 'key', key | first %}
      {% assign items = site.data.publications | where_exp: 'pub', 'pub.areas contains key' %}{% assign title = area.title %}{% assign description = area.description %}
    {% endif %}
    {% if items.size > 0 %}
    <section id="area-{{ key }}" aria-labelledby="area-{{ key }}-title">
      <div class="category-heading"><h2 id="area-{{ key }}-title">{{ title }}</h2><span>{{ items.size | prepend: '0' | slice: -2, 2 }}</span></div>
      {% if description != '' %}<p class="category-description">{{ description }}</p>{% endif %}
      <div class="publication-list">
        {% for publication in items %}{% assign marker = ',' | append: publication.id | append: ',' %}{% if anchored contains marker %}{% include editorial-publication.html publication=publication anchor=false %}{% else %}{% assign anchored = anchored | append: publication.id | append: ',' %}{% include editorial-publication.html publication=publication %}{% endif %}{% endfor %}
      </div>
    </section>
    {% endif %}
  {% endfor %}
  <div class="contribution-notes">
    <p><em>'*' Denotes 'Equal Contribution/ Guidance'</em></p>
    <p><em>'^' Denotes 'Signifiant Contribution'</em></p>
  </div>
</div>
