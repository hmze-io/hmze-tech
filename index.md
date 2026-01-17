---
layout: custom
---

<section>
  {{ page.description }}
  <div class="podcast-player-grid">
    <span><a href="https://open.spotify.com/show/4z2WgPzv2tXcYMHcmdnwVZ"><img src="/assets/img/Spotify.svg" alt="Spotify" /></a></span>
    <span><a href="https://podcasts.google.com/feed/aHR0cHM6Ly9mZWVkLnBvZGJlYW4uY29tL2htemUvZmVlZC54bWw"><img src="/assets/img/GooglePodcasts.png" alt="Google Podcasts" /></a></span>
    <span><a href="https://podcasts.apple.com/de/podcast/hmze/id1552441029"><img src="/assets/img/ApplePodcasts.svg" alt="Apple Podcasts" /></a></span>
    <span><a href="https://anchor.fm/s/10dff5920/podcast/rss"><img src="/assets/img/RSS.png" alt="RSS" class="logo" /></a></span>
  </div>
</section>

<section>
  {% for post in site.posts %}
    {% assign currentYear = post.date | date: "%Y" %}
    {% assign currentMonth = post.date | date: "%B" %}
    
    {% if currentYear != year %}
    <h1 id="{{ currentYear }}" class="section">{{ currentYear }}</h1>
    {% assign year = currentYear %}
    {% endif %}
    
    {% if currentMonth != month %}
    <h2 id="{{ currentMonth }}">{{ currentMonth }}</h2>
    {% assign month = currentMonth %}
    {% endif %}

    <p>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </p>
  {% endfor %}
</section>