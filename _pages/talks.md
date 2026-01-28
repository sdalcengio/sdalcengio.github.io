---
layout: page
title: talks
permalink: /talks/
description: This is a selection of talks. The slides are available in PDF.
nav: true
nav_order: 4
---

<!-- pages/talks.md -->
<figure style="width: 400px; margin: 0 auto 2rem auto; text-align: center;">
  <img src="{{ '/assets/img/summerBoston.jpg' | relative_url }}" alt="summer time in Boston" style="width: 100%; height: auto; border-radius: 8px;">
  <figcaption style="font-size: 0.9rem; color: var(--global-text-color-light); margin-top: 0.5rem;">Summer time in Boston</figcaption>
</figure>

<ul class="talks-list">
  {% assign sorted_talks = site.talks | sort: "date" | reverse %}
  {% for talk in sorted_talks %}
    <li>
      <strong>{{ talk.title }}</strong> — 
      <em>{{ talk.venue }}</em> 
      ({{ talk.date | date: "%B %Y" }})
      {% if talk.location %}<br>{{ talk.location }}{% endif %}
      <div class="talk-links" style="display: inline; margin-left: 1rem;">
        {% if talk.slides %}
          <a href="{{ talk.slides }}" target="_blank" class="btn btn-sm z-depth-0"><i class="far fa-file-pdf"></i> Slides</a>
        {% endif %}
        {% if talk.video %}
          <a href="{{ talk.video }}" target="_blank" class="btn btn-sm z-depth-0"><i class="fas fa-video"></i> Video</a>
        {% endif %}
      </div>
      {% if talk.abstract %}
        <p style="margin-top: 0.5rem; margin-bottom: 1rem;"><em>{{ talk.abstract }}</em></p>
      {% endif %}
    </li>
  {% endfor %}
</ul>
