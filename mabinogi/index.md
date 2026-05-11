---
layout: page
title: "Mabinogi"
permalink: /mabinogi/
---
<style>
  /* 좁은 본문 폭을 메인처럼 넓게 확장합니다 */
  .page .container {
    max-width: 1200px !important; /* 메인 페이지와 비슷한 너비 */
    width: 95% !important;
  }
  
  /* 카드 사이의 간격을 메인과 맞춥니다 */
  .post-container {
    margin-bottom: 30px;
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
