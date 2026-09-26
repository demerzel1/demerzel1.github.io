---
layout: profile
title: Curriculum Vitae
permalink: /cv/
description: Professional experience, education, publications, and awards of Zhaoxin Meng, Industrial PhD at Einride and Doctoral Researcher at Chalmers and the University of Gothenburg.
redirect_from:
  - /resume
  - /resume/
  - /cv-json/
  - /resume-json
---
<header class="page-intro cv-intro">
  <div>
    <h1>Zhaoxin Meng</h1>
    <p>{{ site.data.profile.role }}</p>
    <p class="muted">{{ site.data.profile.team }}</p>
    <p class="muted">{{ site.data.profile.location }}</p>
    {% for email in site.data.profile.emails %}<p class="muted">{{ email.label }} email: <a href="mailto:{{ email.address }}">{{ email.address }}</a></p>{% endfor %}
  </div>
  <button class="print-button" type="button" hidden>Print / Save PDF</button>
</header>
<section class="profile-section">
  <h2>Profile</h2>
  <p>{{ site.data.profile.about }}</p>
  <div class="profile-links">{% for link in site.data.profile.links %}<a href="{{ link.url }}">{{ link.label }}</a>{% endfor %}</div>
</section>
<section class="profile-section"><h2>Experience</h2>{% include profile-experience.html %}</section>
<section class="profile-section"><h2>Education</h2>{% include profile-education.html detailed=true %}</section>
<section class="profile-section"><h2>Publications</h2>{% include profile-publications.html %}</section>
<section class="profile-section"><h2>Patents</h2>{% include profile-patents.html %}</section>
<section class="profile-section"><h2>Awards</h2>{% include profile-awards.html %}</section>
