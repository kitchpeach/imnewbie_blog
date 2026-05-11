---
layout: default
title: "Mabinogi"
permalink: /mabinogi/
---

<style>
  /* 1. 상단 배너(Hero)는 유지하되, 아래 본문만 넓게 조절 */
  .site__content {
    max-width: 1170px !important;
    margin: 40px auto !important;
    padding: 0 15px !important;
  }

  /* 2. 카드 그리드 시스템 (3열 나열의 핵심) */
  .post-list-custom {
    display: flex;
    flex-wrap: wrap;
    margin: 0 -15px; /* 부모 마진 상쇄 */
  }

  .post-card-wrap {
    width: 33.333%; /* 무조건 3열 */
    padding: 15px;
    box-sizing: border-box;
  }

  @media (max-width: 992px) { .post-card-wrap { width: 50%; } }
  @media (max-width: 767px) { .post-card-wrap { width: 100%; } }

  /* 3. 카드 디자인 복제 (그림자, 둥근 모서리) */
  .post-card-custom {
    background: #fff;
    border-radius: 4px;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.05); /* 메인의 부드러운 그림자 */
    height: 100%;
    display: flex;
    flex-direction: column;
    overflow: hidden;
    transition: transform 0.3s ease;
    border: 1px solid #f0f0f0;
  }

  /* 4. 이미지 영역 (높이와 비율) */
  .post-card__thumb-custom {
    position: relative;
    height: 210px;
    overflow: hidden;
    background: #333;
  }

  .post-card__thumb-custom img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  /* 5. 텍스트 영역 여백 */
  .post-card__inner-custom {
    padding: 30px;
    flex-grow: 1;
    display: block;
    text-decoration: none !important;
    color: inherit;
  }

  .post-card__header h2 {
    margin: 0 0 10px 0;
    font-size: 1.4rem;
    line-height: 1.3;
    font-weight: 700;
    color: #333;
  }

  .post-card__meta {
    font-size: 13px;
    color: #bbb;
  }

  .post-card__excerpt {
    margin-top: 15px;
    font-size: 15px;
    line-height: 1.6;
    color: #666;
  }
</style>

<div class="post-list-custom">
  {% for post in site.categories.mabinogi %}
  <div class="post-card-wrap">
    <div class="post-card-custom">
      
      <div class="post-card__thumb-custom">
        <a href="{{ site.baseurl }}{{ post.url }}">
          {% if post.featured-img %}
            <img src="{{ site.baseurl }}/assets/img/posts/{{ post.featured-img }}.jpg" alt="{{ post.title }}">
          {% elsif post.hero_img %}
            <img src="{{ site.baseurl }}/assets/img/{{ post.hero_img }}" alt="{{ post.title }}">
          {% endif %}
        </a>
      </div>

      <a class="post-card__inner-custom" href="{{ site.baseurl }}{{ post.url }}">
        <div class="post-card__header">
          <h2>{{ post.title }}</h2>
          <span class="post-card__meta">{{ post.date | date: "%b %d, %Y" }}</span>
        </div>
        <p class="post-card__excerpt">
          {{ post.content | strip_html | truncatewords: 15 }}
        </p>
      </a>

    </div>
  </div>
  {% endfor %}
</div>