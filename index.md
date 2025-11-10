---
layout: single
title: "Home"
author_profile: false
sidebar:
  nav: "sidebar"
---

{% comment %}
Combine static carousel + recent Radar posts with images
- 静态图：来自 _data/carousel.yml
- 动态图：来自 _posts/ 中 categories 含 'radar' 且有 image 的最近 3 篇
{% endcomment %}

{% assign static_slides = site.data.carousel %}

{%- comment -%} 从 _posts 抓取 Radar 帖子（带 image） {%- endcomment -%}
{% assign radar_posts = site.posts
  | where_exp: "p", "p.categories contains 'radar' and p.image"
  | sort: "date"
  | reverse
  | slice: 0, 3
%}

{%- comment -%} 合并：静态图 + Radar 帖子 {%- endcomment -%}
{% assign slides = static_slides | concat: radar_posts %}

{%- comment -%} 传给轮播组件 {%- endcomment -%}
{% include carousel.html slides=slides %}

