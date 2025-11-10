---
layout: single
title: "Home"
author_profile: false
sidebar:
  nav: "sidebar"
---

{% comment %}
Combine static carousel + recent Radar posts with images
{% endcomment %}
{% assign static_slides = site.data.carousel %}
{% assign radar_pages = site.pages | where_exp: "p", "p.path contains '/radar/'" %}
{% assign radar_with_images = radar_pages | where_exp: "p", "p.image" | sort: "date" | reverse | slice: 0, 3 %}
{% assign slides = static_slides | concat: radar_with_images %}

{% include carousel.html slides=slides %}
