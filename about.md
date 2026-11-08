---
layout: default
title: 소개
permalink: /about/
---
<div class="wrap">

  <div class="post-head">
    <h1>소개</h1>
  </div>

  <div class="prose">
    <p>
      도쿄대학에서 홀 추력기를 연구하는 이지원입니다. 연구 홈페이지는
      <a href="{{ site.home_url }}">여기</a>에 따로 있고, 이 쪽은 남겨둘 만한 것들을
      적어두는 공간입니다.
    </p>

    <p>크게 다섯 갈래로 나눠 씁니다.</p>

    <ul>
      {%- for g in site.data.categories %}
      <li>
        <strong>{{ g.icon }} {{ g.label }}</strong> — {{ g.blurb }}<br>
        {%- for it in g.items %}
        <a href="{{ '/c/' | append: it.key | append: '/' | relative_url }}">{{ it.label }}</a>{% unless forloop.last %} · {% endunless %}
        {%- endfor %}
      </li>
      {%- endfor %}
    </ul>

    <p>
      글은 <a href="{{ '/feed.xml' | relative_url }}">RSS</a>로도 받아볼 수 있습니다.
    </p>
  </div>

</div>
