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
