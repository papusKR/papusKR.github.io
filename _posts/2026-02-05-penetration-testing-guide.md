---
layout: post
title: "모의해킹 가이드"
date: 2026-02-05
categories: [Security, Pentesting]
tags: [pentesting, hacking, security-testing]
description: "윤리적 해킹과 모의해킹 방법론에 대해 알아봅니다."
image: "/assets/img/posts/pentesting.jpg"
---

# 모의해킹 가이드

모의해킹(Penetration Testing)은 시스템의 취약점을 사전에 발견하기 위한 중요한 보안 활동입니다.

## 모의해킹 단계

### 1. 정보 수집 (Reconnaissance)
```bash
# Nmap을 이용한 포트 스캔
nmap -sV -sC target.com

# DNS 정보 수집
dig target.com ANY
```

### 2. 취약점 분석 (Scanning)
- 포트 스캔
- 서비스 버전 확인
- 취약점 데이터베이스 조회

### 3. 접근 획득 (Gaining Access)
발견된 취약점을 이용하여 시스템에 접근합니다.

### 4. 권한 상승 (Privilege Escalation)
일반 사용자 권한을 관리자 권한으로 상승시킵니다.

### 5. 보고서 작성
발견된 취약점과 해결 방안을 문서화합니다.

## 윤리적 고려사항

- 항상 허가된 범위 내에서만 테스트
- 법적 계약 필수
- 데이터 보호 준수

## 추천 도구

- Kali Linux
- Metasploit Framework
- Burp Suite
- Wireshark
