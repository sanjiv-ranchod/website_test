---
layout: default
---

<!-- About Me -->
<section id="about" class="about-section">
  <div class="about-content">
    <div class="about-image">
      <img src="assets/img/profile_pic.jpg" alt="Profile Image">
    </div>
    <div class="about-right">
      <div class="about-text">
        <p> Hi there, my name is Sanjiv and welcome to my academic webpage! A bit about me...</p>
        <p>
        I am a PhD student in Category Theory at the <a href="https://www.cst.cam.ac.uk/" target="_blank">University of Cambridge</a> (United Kingdom) as a <a href="https://www.gatescambridge.org/biography/18554/" target="_blank">Gates Cambridge Scholar</a>, under the supervision on <a href="https://www.cl.cam.ac.uk/~mpf23/" target="_blank">Professor Marcelo Fiore</a>. My broad research interests are in Categorical Logic and Categorical Algebra.
        </p>
        <p>
        More specifically, I am currently working on category theoretic models of substructural theories &mdash; such as Lawvere theories and symmetric operads &mdash; as substitution algebras and substitution monoids, generalisations of species of structure, and abstract syntax of binding and second-order theories. I often make use of aspects of symmetric monoidal- and 2-category theory. I also work on internal category theory in the context of categorical algebra.
        </p>
        <p>
        Previously, I completed my BSc, Honours and Masters degrees at the <a href="https://science.uct.ac.za/departments/mathematics-applied-mathematics" target="_blank">University of Cape Town</a> (South Africa) under the supervision of <a href="https://science.uct.ac.za/department-mathematics/contacts/george-janelidze" target="_blank">Professor George Janelidze</a> during which I spent a year at <a href="https://www.uclouvain.be/fr/instituts-recherche/irmp" target="_blank">Université Catholique de Louvain</a> (Belgium) under the supervision of <a href="https://perso.uclouvain.be/marino.gran/" target="_blank">Professor Marino Gran</a>.
        </p>
      </div>
      <div class="about-contact">
        <div class="about-email-box">
        Email : <a href="mailto:sanjiv.ranchod@cl.cam.ac.uk" class="about-email">sanjiv.ranchod@cl.cam.ac.uk</a>
        </div>
        <div class="about-buttons">
          <a href="https://scholar.google.com/citations?user=mLMt8jsAAAAJ&hl=en&oi=ao" target="_blank" class="btn google-scholar">Scholar</a>
          <a href="https://orcid.org/0000-0003-0334-7010" target="_blank" class="btn orcid">ORCID</a>
        </div>
      </div>
    </div>
  </div>
  <div class="scroll-down">
  <a class="card" href="#papers" aria-label="Scroll to Papers section">
    ↓
  </a>
</div>
</section>

<!-- Papers -->
<section id="papers" class="papers-section">
  <div class="papers-container section-container">
    <h2 class="section-title card">Papers</h2>
    <div class="card-list">
    {% assign sorted_papers = site.data.papers.publications | sort: "date" | reverse %}
    {% for paper in sorted_papers %}
      <div class="paper-entry card">
        <h4 class="paper-title">
          {% if paper.link %}
            <a href="{{ paper.link }}" target="_blank">{{ paper.title }}</a>
          {% else %}
            {{ paper.title }}
          {% endif %}
        </h4>
        <p class="paper-details"> <em>with</em> {{ paper.authors }}</p>
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
      </div>
    {% endfor %}
    </div>
  </div>
</section>

<!-- Talks & Posters -->
<section id="talks-posters" class="talks-section">
  <div class="talks-container section-container">
    <h2 class="section-title card">Talks & Posters</h2>
    <div class="card-list">
    {% assign sorted_talks = site.data.talks.talks | sort: "date" | reverse %}
    {% for talk in sorted_talks %}
      <div class="talk-entry card">
        <h4 class="talk-title">
          {% if talk.link %}
            <a href="{{ talk.link }}" target="_blank">{{ talk.title }}</a>
          {% else %}
            {{ talk.title }}
          {% endif %}
        </h4>
        <p class="talk-details">
          <em>{{ talk.type }} at</em> {{ talk.event }}
        </p>
        <p class="talk-year">{% if talk.upcoming%}Upcoming, {% endif %}{{ talk.year }}</p>
        <div class="talk-links">
          {% if talk.abstract %}
            <a class="btn" href="{{ talk.abstract }}" target="_blank" rel="noopener">Abstract</a>
          {% endif %}
          {% if talk.recording %}
            <a class="btn" href="{{ talk.recording }}" target="_blank" rel="noopener">Recording</a>
          {% endif %}
          {% if talk.slides %}
            <a class="btn" href="{{ talk.slides }}" target="_blank" rel="noopener">Slides</a>
          {% endif %}
        </div>
      </div>
    {% endfor %}
    </div>
  </div>
</section>
