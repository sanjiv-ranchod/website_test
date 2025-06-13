---
layout: default
---

<!-- About Me -->
<section id="about" class="about-section">
  <div class="about-content">
    <div class="about-image">
      <img src="https://via.placeholder.com/200" alt="Profile Image">
    </div>
    <div class="about-text">
      <h2>About Me</h2>
      <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer nec odio. Praesent libero. Sed cursus ante dapibus diam.</p>
    </div>
  </div>
</section>

<!-- Papers -->
<section id="papers" class="papers-section">
  <div class="papers-container section-container">
    <h2 class="section-title">Papers</h2>
    <div class="card-list">
    {% assign sorted_papers = site.data.papers.publications | sort: "year" | reverse %}
    {% for paper in sorted_papers %}
      <div class="paper-entry card">
        <h4 class="paper-title">
          {% if paper.link %}
            <a href="{{ paper.link }}" target="_blank">{{ paper.title }}</a>
          {% else %}
            {{ paper.title }}
          {% endif %}
        </h4>
        <p class="paper-details">with {{ paper.authors }}</p>
        <p class="paper-journal">{{ paper.journal }}</p>
        <p class="paper-year">{{ paper.year }}</p>
        <div class="paper-links">
          {% if paper.arxiv %}
            <a class="btn" href="{{ paper.arxiv }}" target="_blank">arXiv</a>
          {% endif %}
          {% if paper.pdf %}
            <a class="btn" href="{{ paper.pdf }}" target="_blank">PDF</a>
          {% endif %}
        </div>
        <hr>
      </div>
    {% endfor %}
    </div>
  </div>
</section>

<!-- Talks & Posters -->
<section id="talks-posters" class="talks-section">
  <div class="talks-container section-container">
    <h2 class="section-title">Talks & Posters</h2>
    <div class="card-list">
    {% assign sorted_talks = site.data.talks.talks | sort: "year" | reverse %}
    {% for talk in sorted_talks %}
      <div class="talk-entry card">
        <h4 class="talk-title">{{ talk.title }}</h4>
        <p class="talk-details">
          {{ talk.type }} at <strong>{{ talk.event }}</strong>
          {% if talk.location %}, {{ talk.location }}{% endif %}
        </p>
        <p class="talk-year">{{ talk.year }}</p>
        <div class="talk-links">
          {% if talk.link %}
            <a class="btn" href="{{ talk.link }}" target="_blank" rel="noopener">Link</a>
          {% endif %}
          {% if talk.pdf %}
            <a class="btn" href="{{ talk.pdf }}" target="_blank" rel="noopener">PDF</a>
          {% endif %}
        </div>
        <hr>
      </div>
    {% endfor %}
    </div>
  </div>
</section>
