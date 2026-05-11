---
layout: default
title: "Mabinogi"
permalink: /mabinogi/
---

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