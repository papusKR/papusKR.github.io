---
layout: page
title: 소개
permalink: /about/
description: "외양간을 고치는 사람이 되고자 합니다. 소를 잃기 전에 외양간을 고치듯, 자산을 잃기 전에 공격을 분석하고 실험하고 기록합니다."
---

<div class="face" markdown="0">
  {% if site.avatar %}<img class="pic" src="{{ site.avatar | relative_url }}" alt="{{ site.name }}">
  {% else %}<div class="mono" aria-hidden="true">pK</div>{% endif %}
  <div>
    <p class="nm">{{ site.name }}</p>
    <p class="rl">{{ site.role }}</p>
  </div>
</div>

## 지금

한국의 보안 기업에서 원격으로 고객사 보안관제 업무를 하고 있습니다.

## 할 수 있는 것

- 정찰성 트래픽 분석
- 웹 공격 정오탐 판별 및 이벤트 보고서 작성
- 탐지 이벤트 분석 기반 SOAR 룰 생성 및 개선

## 앞으로

관제에서 보안 운영으로 범위를 넓히려고 합니다.
탐지룰을 직접 설계하고, 침해대응과 위협 헌팅까지 다루는 쪽입니다.
나아가 국방·안보 환경에 특화된 보안 운영에 닿는 것이 목표입니다.
국가 단위 위협을 상대하고 엄격한 절차와 문서화가 요구되는 영역입니다.

## 자격

- 정보처리기사
- 리눅스마스터 2급
- SQLD

## 연락

{% if site.email and site.email != "" %}- Email — [{{ site.email }}](mailto:{{ site.email }})
{% endif %}{% if site.github_user and site.github_user != "" %}- GitHub — [github.com/{{ site.github_user }}](https://github.com/{{ site.github_user }})
{% endif %}{% if site.linkedin_url and site.linkedin_url != "" %}- LinkedIn — [프로필]({{ site.linkedin_url }})
{% endif %}
