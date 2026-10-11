---
layout: editorial
permalink: /
title: "Leyao (Laura) Wang"
redirect_from:
  - /about/
  - /about.html
---

<section class="hero" id="about" aria-labelledby="hero-title">
  <div class="shell hero-grid">
    <div class="hero-copy">
      <p class="eyebrow">Researcher · Yale University</p>
      <h1 id="hero-title">Leyao <span class="name-nickname">(Laura)</span> Wang</h1>
      <p class="hero-affiliation">MSCS (thesis-track) · Yale University · New Haven, CT</p>
      <p class="hero-statement">My research focuses on continual learning and adaptation in language models and AI agents.</p>
      <ul class="profile-links" aria-label="Academic and contact links">
        <li><a href="{{ site.author.googlescholar | escape }}">Google Scholar ↗</a></li>
        <li><a href="https://github.com/{{ site.author.github | escape }}">GitHub ↗</a></li>
        <li><a href="https://www.linkedin.com/in/{{ site.author.linkedin | escape }}/">LinkedIn ↗</a></li>
        <li><a href="mailto:{{ site.author.email | escape }}">Email ↗</a></li>
        <li><a href="{{ '/cv/' | relative_url }}">CV ↗</a></li>
      </ul>
      <div class="hero-biography">
        <p>Welcome! I am Leyao (Laura) Wang, a <a href="https://engineering.yale.edu/academic-study/departments/computer-science/graduate-study/master-science-program"> MSCS (thesis-track) </a> at <a href="https://www.yale.edu/"> Yale University</a> co-advised by Prof. <a href="https://www.cs.yale.edu/homes/ying-rex/"> Rex Ying</a> and Prof. <a href="https://armancohan.com/"> Arman Cohan</a>. I obtained the Bachelor of Science from <a href="https://www.vanderbilt.edu/"> Vanderbilt University</a> with <a href="https://registrar.vanderbilt.edu/academic-records/latin-honors.php"> summa cum laude </a> (the highest honor), double majoring in <a href="https://engineering.vanderbilt.edu/departments/computer-science/"> Computer Science</a> and <a href="https://as.vanderbilt.edu/math/"> Mathematics</a> and minoring in <a href="https://www.vanderbilt.edu/datascience/"> Data Science</a>. In the past, I was fortunate to work with Dr.<a href="https://tylersnetwork.github.io/"> Tyler Derr</a> and Dr. <a href="https://www.vumc.org/biostatistics/person/zhijun-yin/"> Zhijun Yin</a> at Vanderbilt University, Dr. <a href="https://bme.duke.edu/people/pranam-chatterjee/"> Pranam Chatterjee</a> at Duke University, and  Dr. <a href="https://people.csail.mit.edu/winstonchen/">Wenqiang Chen</a> from CSAIL at MIT.</p>
      </div>
    </div>
    <figure class="hero-portrait">
      <img src="{{ '/images/laura2.png' | relative_url }}" width="2575" height="3417" alt="Portrait of Leyao (Laura) Wang" fetchpriority="high" decoding="async">
    </figure>
  </div>
</section>

<section class="section" id="research" aria-labelledby="research-title">
  <div class="shell">
    <div class="section-heading">
      <div><p class="section-kicker">01 / Research</p><h2 id="research-title">Research interests</h2></div>
    </div>
    <p class="section-lead">My research focuses on <strong>continual learning and adaptation</strong> in <strong>language models and AI agents</strong>. I aim to build systems that keep improving after deployment while retaining what they have learned and correcting their own mistakes. My work spans three connected directions:</p>
    <div class="research-grid">
      <article class="research-card">
        <span class="research-number">01</span>
        <h3>Self-improvement from imperfect supervision</h3>
        <p>Data-centric methods and training strategies, such as on-policy self-distillation and RL post-training, that let models learn from noisy, sparse, or self-generated signals.</p>
      </article>
      <article class="research-card">
        <span class="research-number">02</span>
        <h3>Long-horizon personalization</h3>
        <p>Agents that learn from sustained human interaction, maintain evolving user representations, and adapt as preferences and needs change.</p>
      </article>
      <article class="research-card">
        <span class="research-number">03</span>
        <h3>Evaluation and oversight of adaptive systems</h3>
        <p>Reliable methods for assessing agent behavior, detecting unreliable feedback, and preventing error accumulation during continual learning.</p>
      </article>
    </div>
  </div>
</section>

<section class="section" id="selected-publications" aria-labelledby="selected-title">
  <div class="shell">
    <div class="section-heading">
      <div><p class="section-kicker">02 / Selected work</p><h2 id="selected-title">Selected publications</h2></div>
      <a class="text-link" href="{{ '/publications/' | relative_url }}">All publications <span aria-hidden="true">↗</span></a>
    </div>
    <div class="publication-list">
      {% for publication in site.data.publications %}
        {% if publication.selected %}{% include editorial-publication.html publication=publication %}{% endif %}
      {% endfor %}
    </div>
  </div>
</section>

<section class="section" id="news" aria-labelledby="news-title">
  <div class="shell">
    <div class="section-heading">
      <div><p class="section-kicker">03 / Updates</p><h2 id="news-title">News</h2></div>
    </div>
    <ol class="news-list">
      {% for item in site.data.news limit:6 %}
        {% assign month = item.date | slice: 0, 2 %}{% assign year = item.date | slice: 3, 4 %}
        <li><time datetime="{{ year }}-{{ month }}">{{ item.date }}</time><div class="news-copy">{{ item.body | markdownify }}</div></li>
      {% endfor %}
    </ol>
    <details class="news-more">
      <summary>View all updates</summary>
      <ol class="news-list" start="7">
        {% for item in site.data.news offset:6 %}
          {% assign month = item.date | slice: 0, 2 %}{% assign year = item.date | slice: 3, 4 %}
          <li><time datetime="{{ year }}-{{ month }}">{{ item.date }}</time><div class="news-copy">{{ item.body | markdownify }}</div></li>
        {% endfor %}
      </ol>
    </details>
  </div>
</section>
