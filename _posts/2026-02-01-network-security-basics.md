---
layout: post
title: "네트워크 보안 기초"
date: 2026-02-01
categories: [Network/Security, Security/Firewall]
tags: [firewall, ids, ips, network-security]
description: "네트워크 보안의 기본 개념과 주요 기술을 설명합니다."
image: "/assets/img/posts/network-security.jpg"
---

# 네트워크 보안 기초

네트워크 보안은 네트워크 인프라와 데이터를 무단 접근, 오용, 수정으로부터 보호하는 것입니다.

## 방화벽 (Firewall)

### iptables 규칙 예제
```bash
# 기본 정책 설정
sudo iptables -P INPUT DROP
sudo iptables -P FORWARD DROP
sudo iptables -P OUTPUT ACCEPT

# SSH 허용
sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT

# HTTP/HTTPS 허용
sudo iptables -A INPUT -p tcp --dport 80 -j ACCEPT
sudo iptables -A INPUT -p tcp --dport 443 -j ACCEPT
```

## IDS/IPS (침입 탐지/방지 시스템)

### Snort 규칙
```
alert tcp any any -> $HOME_NET 22 (msg:"SSH Brute Force Attempt"; 
  flags:S; threshold: type threshold, track by_src, count 5, seconds 60; 
  sid:1000001;)
```

## VPN (가상 사설망)

VPN은 공용 네트워크를 통해 안전한 연결을 제공합니다.

## 네트워크 세그멘테이션

```
[Internet]
    |
[Firewall]
    |
    +-- [DMZ] - Web Servers
    |
    +-- [Internal Network]
        |
        +-- [User VLAN]
        +-- [Server VLAN]
        +-- [Management VLAN]
```

## 결론

계층적 보안 전략(Defense in Depth)을 통해 네트워크를 보호해야 합니다.
