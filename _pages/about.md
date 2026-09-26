---
layout: profile
permalink: /
title: About
description: Zhaoxin Meng is an Industrial PhD at Einride and Doctoral Researcher at Chalmers and the University of Gothenburg in Gothenburg, Sweden. Current research focuses on AI agents.
redirect_from:
  - /about/
  - /about.html
---
{% assign profile = site.data.profile %}
<section class="intro" aria-labelledby="intro-title">
  <div class="intro-heading">
    <div class="intro-identity">
      <h1 id="intro-title">{{ profile.name }}</h1>
      <p class="intro-role">Industrial PhD at Einride, Doctoral Researcher at Chalmers and GU.</p>
      <p class="muted">{{ profile.location }}</p>
      <div class="profile-links">
        {% for link in profile.links %}<a href="{{ link.url }}">{{ link.label }}</a>{% endfor %}
        {% for email in profile.emails %}<a href="mailto:{{ email.address }}">{{ email.label }} email</a>{% endfor %}
      </div>
    </div>
    <img class="profile-portrait" src="{{ profile.portrait | relative_url }}" alt="Portrait of Zhaoxin Meng" width="420" height="564" fetchpriority="high">
  </div>
  <p class="intro-bio">{{ profile.about }}</p>
  <p class="muted">My background spans robotics, autonomous driving, 3D perception, and multi-modal learning.</p>
  <div class="affiliation-logos" aria-label="Research institutions and funding">
    {% for key in profile.affiliations %}
    {% assign org = site.data.organizations[key] %}
    <a class="affiliation-logo" href="{{ org.url }}">
      <img src="{{ org.logo | relative_url }}" alt="" width="144" height="52">
      <span>{{ org.label }}</span>
    </a>
    {% endfor %}
  </div>
</section>
<section id="experience" class="profile-section" aria-labelledby="experience-title">
  <div class="section-topline"><h2 id="experience-title">Experience</h2><a href="{{ '/cv/' | relative_url }}">Full CV</a></div>
  {% include profile-experience.html %}
</section>
<section class="profile-section" aria-labelledby="research-title">
  <div class="section-topline"><h2 id="research-title">Selected publications</h2><a href="{{ '/publications/' | relative_url }}">All research</a></div>
  {% include profile-publications.html %}
</section>
<section class="profile-section" aria-labelledby="education-title">
  <h2 id="education-title">Education</h2>
  {% include profile-education.html %}
</section>
<section class="profile-section" aria-labelledby="awards-title">
  <h2 id="awards-title">Awards</h2>
  {% include profile-awards.html %}
</section>
<section class="profile-section interests-section" aria-labelledby="interests-title">
  <div>
    <h2 id="interests-title">Personal interests</h2>
    <p>{{ profile.interests }}</p>
  </div>
</section>
