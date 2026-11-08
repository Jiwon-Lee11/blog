---
layout: default
title: 전체 글
permalink: /archive/
---
<div class="wrap">

  <div class="hero">
    <h1>전체 글</h1>
    <p>지금까지 {{ site.posts | size }}개.</p>
  </div>

  {%- if site.posts.size > 0 %}
  {%- assign years = site.posts | group_by_exp: "p", "p.date | date: '%Y'" %}
  {%- for y in years %}
  <div class="sec-head">
    <h2>{{ y.name }}</h2>
    <span class="en">{{ y.items | size }} posts</span>
  </div>
  <ul class="post-list">
    {%- for p in y.items %}{% include post-card.html post=p %}{% endfor %}
  </ul>
  {%- endfor %}
  {%- else %}
  <div class="empty-note">아직 글이 없습니다.</div>
  {%- endif %}

</div>
