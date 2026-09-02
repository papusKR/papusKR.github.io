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

## 지금

정보보안 관제 업무를 하고 있습니다. 하루의 대부분은 알람을 보고,
정탐과 오탐을 가르고, 필요하면 위로 올리는 일로 채워집니다.
주로 보는 것은 포트 스캔과 스윕, 세션 연결 시도, DNS, 웹 공격입니다.

## 앞으로

보안운영과 침해대응(CERT) 쪽으로 가려고 합니다. 알람을 처리하는 데서
그치지 않고, 탐지 자체를 설계하고 사고 이후를 정리하는 일까지 하고 싶습니다.

## 다루는 것

<div class="duo" markdown="0">
  <div class="block">
    <h4>탐지 · 분석</h4>
    <ul>
      <li>IPS · WAF 알람 트리아지</li>
      <li>스캔 · 정찰 트래픽 판별</li>
      <li>웹 공격 패턴 분석</li>
    </ul>
  </div>
  <div class="block">
    <h4>네트워크</h4>
    <ul>
      <li>패킷 분석</li>
      <li>방화벽 정책</li>
      <li>세션 · 트래픽 흐름 추적</li>
    </ul>
  </div>
</div>
<div class="duo" markdown="0">
  <div class="block">
    <h4>도구</h4>
    <ul>
      <li>Wireshark · tcpdump</li>
      <li>nmap</li>
      <li>SIEM</li>
    </ul>
  </div>
  <div class="block">
    <h4>공부하는 것</h4>
    <ul>
      <li>Sigma 룰 작성</li>
      <li>MITRE ATT&amp;CK 매핑</li>
      <li>로그 파싱 자동화</li>
    </ul>
  </div>
</div>

<p style="font-size:13px;color:#6B6D72;margin:14px 0 0">
위 네 칸은 예시입니다. 실제로 다루시는 범위로 바꿔 쓰세요.
벤더명이나 고객사가 특정될 만한 표현은 넣지 않는 편이 안전합니다.
</p>

## 자격

| 항목 | 상태 |
|---|---|
| 정보처리기사 | — |
| 정보보안기사 | — |
| 네트워크관리사 | — |

## 연락

{% if site.email and site.email != "" %}- Email — [{{ site.email }}](mailto:{{ site.email }})
{% endif %}{% if site.github_user and site.github_user != "" %}- GitHub — [github.com/{{ site.github_user }}](https://github.com/{{ site.github_user }})
{% endif %}{% if site.linkedin_url and site.linkedin_url != "" %}- LinkedIn — [프로필]({{ site.linkedin_url }})
{% endif %}
