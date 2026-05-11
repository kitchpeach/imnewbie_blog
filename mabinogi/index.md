---
layout: page
title: "Mabinogi"
permalink: /mabinogi/
---
<style>
  /* 1. 아임뉴비님이 말씀하신 내부 여백(Padding) 강제 적용 */
  .post-card__content, .post-card__inner {
    padding: 30px !important; /* 메인 페이지의 시원한 여백 값 */
    background: #fff; /* 카드 배경색 */
  }

  /* 2. 제목과 날짜 사이의 간격 조정 */
  .post-card__title {
    margin-top: 0 !important;
    margin-bottom: 10px !important;
    font-size: 1.4rem !important; /* 메인과 폰트 크기 맞춤 */
  }

  /* 3. 요약글(Excerpt) 여백 */
  .post-card__excerpt {
    margin-bottom: 0 !important;
    color: #666;
  }

  /* 4. 카드 자체에 그림자나 테두리가 없다면 추가 (선택사항) */
  .post-card {
    border: 1px solid #eee;
    border-radius: 5px;
    overflow: hidden;
    height: 100%; /* 카드 높이 통일 */
  }
</style>

<div class="row">
  {% for post in site.categories.mabinogi %}
  <div class="col-xs-12 col-sm-6 col-md-4 post-container">
    <div class="post-card">
      <a href="{{ site.baseurl }}{{ post.url }}" class="post-card__image-link">
        {% if post.hero_img %}
          <div class="post-card__image" style="background-image: url('{{ site.baseurl }}/assets/img/{{ post.hero_img }}')"></div>
        {% else %}
          <div class="post-card__image" style="background-color: #333"></div>
        {% endif %}
      </a>
      <div class="post-card__content">
        <a href="{{ site.baseurl }}{{ post.url }}">
          <h2 class="post-card__title">{{ post.title }}</h2>
        </a>
        <p class="post-card__date">{{ post.date | date: "%b %d, %Y" }}</p>
        <p class="post-card__excerpt">{{ post.content | strip_html | truncatewords: 15 }}</p>
      </div>
    </div>
  </div>
  {% endfor %}
</div>
