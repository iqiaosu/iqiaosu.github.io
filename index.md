---
layout: single
title: ""
author_profile: false
sidebar:
  nav: "sidebar"
---

<!-- Home 专属背景 + 叠层，只包住轮播区域 -->
<style>
.home-hero {
  position: relative;
  margin: 0 auto 1.25rem auto;
  border-radius: 14px;              /* 圆角可调，想直角就设为 0 */
  overflow: hidden;
}
/* 背景图 */
.home-hero::before {
  content: "";
  position: absolute;
  inset: 0;
  background: url('/assets/images/headhover-home.jpg') center center / cover no-repeat fixed;
  filter: brightness(.65);          /* 暗一点，让内容更清晰；0.5更暗，0.8更亮 */
}
/* 叠层里的内容（你的轮播）保持在前景 */
.home-hero > .home-hero__content {
  position: relative;
  padding: 1rem;                    /* 让轮播四周留点呼吸空间 */
}
@media (max-width: 768px) {
  .home-hero { border-radius: 10px; }
  .home-hero > .home-hero__content { padding: .5rem; }
}
</style>

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

{%- comment -%} 交给轮播组件渲染（外面包一层带背景的容器） {%- endcomment -%}
<div class="home-hero">
  <div class="home-hero__content">
    {% include carousel.html slides=slides %}
  </div>
</div>
