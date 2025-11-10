---
layout: single
title: "Home"
author_profile: false
sidebar:
  nav: "sidebar"
---

{% comment %}
Combine static carousel + recent posts with images
- 静态图：_data/carousel.yml
- 动态图：从 _posts/ 中挑 front matter 里有 image 的文章，
  且分类包含 radar / technology / woohoo / literature 任一类
{% endcomment %}

{% assign static_slides = site.data.carousel %}

{%- comment -%} 先取所有“有图”的文章 {%- endcomment -%}
{% assign posts_with_image = site.posts | where_exp: "p", "p.image" %}

{%- comment -%} 再按分类过滤（不使用括号） {%- endcomment -%}
{% assign picked_posts = posts_with_image
  | where_exp: "p", "p.categories contains 'radar' or p.categories contains 'technology' or p.categories contains 'woohoo' or p.categories contains 'literature'"
  | sort: "date"
  | reverse
  | slice: 0, 6
%}

{%- comment -%} 合并静态图 + 动态图 {%- endcomment -%}
{% assign slides = static_slides | concat: picked_posts %}

{%- comment -%} 交给轮播组件渲染 {%- endcomment -%}
{% include carousel.html slides=slides %}
