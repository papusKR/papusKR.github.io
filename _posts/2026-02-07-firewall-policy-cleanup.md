---
title: "방화벽 정책 정리 작업 기록"
date: 2026-02-07
categories: [Operations, Firewall]
tags: [firewall, policy, iptables, audit]
description: "쓰지 않는 규칙 400개를 걷어내면서 세운 기준과, 지우다 사고 날 뻔한 이야기."
---

더미 글입니다.

## 기준

1. 최근 90일간 히트 카운트 0
2. 목적지가 이미 폐기된 자산
3. any-any 규칙

## 확인

```bash
# 히트 카운트 확인
sudo iptables -L -v -n --line-numbers

# 0인 규칙만 추리기
sudo iptables -L -v -n --line-numbers | awk '$1 == 0'
```

## 사고 날 뻔한 부분

히트 카운트가 0이어도 **분기 배치에서만 쓰는 경로**가 있었습니다.
90일 기준으로는 안 잡힙니다. 담당자 확인 없이 지웠으면 월말에 터졌을 겁니다.

> 히트 카운트는 필요조건이지 충분조건이 아닙니다.
