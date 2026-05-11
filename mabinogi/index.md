---
layout: page
title: "Mabinogi"
permalink: /mabinogi/
---

<style>
  /* 메인 페이지의 넓은 컨테이너 복제 */
  .page .container {
    max-width: 1170px !important;
    width: 100% !important;
    margin: 0 auto !important;
  }

  /* 카드 이미지 영역: 메인과 동일한 비율과 디자인 */
  .post-card__thumb {
    position: relative;
    position: relative;
    display: block;
    background-color: #333; /* 이미지 없을 때 배경색 */
    height: 210px;
    overflow: hidden;
    margin: 0;
  }

  .post-card__thumb img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  /* 카테고리 뱃지 디자인 (메인과 동일) */
  .post-card__label {
    position: absolute;
    top: 15px;
    left: 15px;
    z-index: 10;
  }

  .label {
    background: rgba(255,255,255,0.2);
    color: #fff;
    padding: 3px 10px;
    border-radius: 20px;
    font-size: 11px;
    text-transform: uppercase;
    border: 1px solid rgba(255,255,255,0.5);
  }

  /* 카드 내부 텍스트 여백 */
  .post-card__inner {
    padding: 30px !important;
    display: block;
    text-decoration: none !important;
  }

  .post-card {
    background: #fff;
    border-radius: 4px;
    box-shadow: 0 2px 10px rgba(0,0,0,0.05);
    overflow: hidden;
    height: 100%;
    border: 1px solid #eee;
  }
</style>

<div class="row">
  {% for post in site.categories.mabinogi %}
  <div class="col-xs-12 col-sm-6 col-md-4 post-container" style="margin-bottom: 30px;">
    <div class="post-card">
      
      <div class="post-card__thumb">
        <span class="post-card__label">
          <span class="label">Mabinogi</span>
        </span>
        <a href="{{ site.baseurl }}{{ post.url }}">
          {% if post.featured-img %}
            <img src="{{ site.baseurl }}/assets/img/posts/{{ post.featured-img }}.jpg" alt="{{ post.title }}">
          {% elsif post.hero_img %}
            <img src="{{ site.baseurl }}/assets/img/{{ post.hero_img }}" alt="{{ post.title }}">
          {% endif %}
        </a>
      </div>

      <a class="post-card__inner" href="{{ site.baseurl }}{{ post.url }}">
        <div class="post-card__header">
          <h2 class="post-card__title" style="font-size: 1.4rem; margin-top: 0; color: #333;">{{ post.title }}</h2>
          <span class="post-card__meta" style="color: #999; font-size: 13px;">{{ post.date | date: "%b %d, %Y" }}</span>
        </div>
        <p class="post-card__excerpt" style="color: #666; margin-top: 15px;">
          {{ post.content | strip_html | truncatewords: 15 }}
        </p>
      </a>

    </div>
  </div>
  {% endfor %}
</div>