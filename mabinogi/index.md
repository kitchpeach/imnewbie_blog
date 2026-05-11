---
layout: page
title: "Mabinogi"
permalink: /mabinogi/
---
<style>
  /* 1. 컨테이너 너비를 메인과 동일하게 1170px로 고정 */
  .page .container {
    max-width: 1170px !important;
    width: 100% !important;
    margin: 0 auto !important;
    padding: 0 15px !important;
  }

  /* 2. 카드 한 개의 너비를 메인(33.333%)과 똑같이 강제 고정 */
  @media (min-width: 992px) {
    .post-container {
      width: 33.33333333% !important; /* PC에서 무조건 3단 배열 크기 */
      float: left; /* 그리드가 깨질 경우를 대비 */
    }
  }

  /* 3. 아까 찾으신 내부 패딩과 높이값 고정 */
  .post-card {
    display: block;
    min-height: 400px; /* 전체 카드 높이 감각 맞추기 */
    background: #fff;
    border: 1px solid #efefef;
    box-shadow: 0 2px 5px rgba(0,0,0,0.05); /* 메인 같은 은은한 그림자 */
  }

  .post-card__content {
    padding: 30px !important;
  }

  .post-card__image {
    height: 210px !important; /* 이미지 영역 높이 고정 */
    background-size: cover;
    background-position: center;
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
