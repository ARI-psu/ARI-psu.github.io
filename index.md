---
title: ARI Lab
subtitle: We research Aerial Robots & Interaction 
layout: page
show_sidebar: false
hide_footer: false
hero_height: is-large
hero_image: /img/posts/2020-12-19-multilift/outdoor_short.gif
hero_link: /research/
hero_link_text: See Our Research

hero_link2: /publications/
hero_link_text2: See Our Publication
---

# About Us

Our mission is to advance state-of-the-art aerial autonomy by bridging the aerospace and robotic communities. 

We are proud to be part of the [Deparment of Aerospace Engineering](https://www.aero.psu.edu/) at [Pennsylvania State University](https://www.psu.edu/). 


# Highlights
{% assign posts = site.posts | where:"categories","highlights" %}
<div class="columns is-multiline">
    {% for post in posts %}
    <div class="column is-3-desktop is-6-tablet">
        {% include post-card.html %}
    </div>
    {% endfor %}
</div>

# Latest News
<!-- {% assign news = site.posts | where:"categories","news" | slice: 0, 3 %}
<div class="columns is-multiline">
    {% for post in news %}
    <div class="column is-3-desktop is-6-tablet">
        {% include post-card.html %}
    </div>
    {% endfor %}
</div>

<p class="has-text-centered">
    <a href="/news" class="button is-primary">See All News</a>
</p> -->

<ul>
  {% assign news = site.posts | where: "categories", "news" | sort: "date" | reverse | slice: 0, 5 %}
  {% for post in news %}
    <li>
      <strong style="color: red;">{{ post.date | date: "%m/%Y" }}</strong>: 
      {{ post.title | strip_html | truncatewords: 30 }} 
      <!-- {% if post.url %}<a href="{{ post.url }}" target="_blank">🔗</a>{% endif %} -->
    </li>
  {% endfor %}
</ul>

<p class="has-text-centered">
    <a href="/news" class="button is-primary">See All News</a>
</p>