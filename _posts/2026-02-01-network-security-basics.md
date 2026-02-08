---
layout: post
title: "Test"
date: 2026-02-01
categories: [Security, Network]
tags: [firewall, network, security]
description: "네트워크 보안의 기본 개념과 방화벽 설정 방법을 알아봅니다."
image: "/assets/img/posts/network-security.jpg"
---

# 네트워크 보안 기초

네트워크 보안은 현대 IT 인프라에서 가장 중요한 요소 중 하나입니다.

## 주요 개념

### 1. 방화벽 (Firewall)
방화벽은 네트워크 트래픽을 모니터링하고 제어하는 보안 시스템입니다.

```bash
# iptables 기본 설정
sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT
sudo iptables -A INPUT -p tcp --dport 80 -j ACCEPT
sudo iptables -A INPUT -p tcp --dport 443 -j ACCEPT
```

### 2. 침입 탐지 시스템 (IDS)
IDS는 네트워크에서 악의적인 활동을 탐지합니다.

### 3. VPN
가상 사설망을 통해 안전한 원격 접속을 제공합니다.

## 결론

네트워크 보안은 지속적인 모니터링과 업데이트가 필요합니다.
