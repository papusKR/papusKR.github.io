---
layout: page
title: 소개
permalink: /about/
description: "무엇을 하는 사람이고 어디로 가려는지."
---

<div class="face" markdown="0">
  {% if site.avatar %}<img class="pic" src="{{ site.avatar | relative_url }}" alt="{{ site.name }}">
  {% else %}<div class="mono" aria-hidden="true">pK</div>{% endif %}
  <div>
    <p class="nm">{{ site.name }}</p>
    <p class="rl">{{ site.role }}</p>
    <p class="tg">{{ site.tagline }}</p>
  </div>
</div>

<p style="font-size:13px;color:#6B6D72;margin:0 0 26px">
이 페이지도 뼈대입니다. <code>about.md</code> 를 열어 채우세요.
</p>

## 지금

정보보안 관제 업무를 하고 있습니다. 하루의 대부분은 알람을 보고,
정탐과 오탐을 가르고, 필요하면 위로 올리는 일로 채워집니다.

## 앞으로

보안운영과 침해대응(CERT) 쪽으로 가려고 합니다. 알람을 처리하는 데서
그치지 않고, 탐지 자체를 설계하고 사고 이후를 정리하는 일까지 하고 싶습니다.

## 카테고리

- **Detection** — 룰을 쓰고 튜닝한 기록
- **Analysis** — 재현하고 분석한 케이스
- **Operations** — 운영하며 만든 것
- **Notes** — 학습 메모

## 연락

{% if site.email and site.email != "" %}- Email — [{{ site.email }}](mailto:{{ site.email }})
{% endif %}{% if site.github_user and site.github_user != "" %}- GitHub — [github.com/{{ site.github_user }}](https://github.com/{{ site.github_user }})
{% endif %}{% if site.linkedin_url and site.linkedin_url != "" %}- LinkedIn — [프로필]({{ site.linkedin_url }})
{% endif %}- RSS — [feed.xml]({{ '/feed.xml' | relative_url }})

`_config.yml` 의 `email`, `github_user`, `linkedin_url` 을 채우면 위 목록에 자동으로 나타납니다.
