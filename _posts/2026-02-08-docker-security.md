---
layout: post
title: "Docker 컨테이너 보안"
date: 2026-02-08
categories: [Security/Container, Cloud/Docker]
tags: [docker, container, devops, security]
description: "Docker 컨테이너 환경에서의 보안 모범 사례를 알아봅니다."
image: "/assets/img/posts/docker-security.jpg"
---

# Docker 컨테이너 보안

Docker는 현대 애플리케이션 배포의 표준이 되었지만, 보안에 주의를 기울여야 합니다.

## 주요 보안 원칙

### 1. 최소 권한 원칙

```dockerfile
# 루트 사용자 대신 일반 사용자 사용
FROM node:18-alpine
RUN addgroup -g 1001 -S nodejs
RUN adduser -S nodejs -u 1001
USER nodejs
```

### 2. 이미지 스캔

```bash
# Trivy를 이용한 취약점 스캔
trivy image myapp:latest

# Docker Scout 사용
docker scout cves myapp:latest
```

### 3. 보안 설정

```yaml
# docker-compose.yml
services:
  app:
    image: myapp:latest
    security_opt:
      - no-new-privileges:true
    cap_drop:
      - ALL
    cap_add:
      - NET_BIND_SERVICE
    read_only: true
```

### 4. 네트워크 격리

```bash
# 커스텀 네트워크 생성
docker network create --driver bridge isolated_network

# 컨테이너를 격리된 네트워크에 연결
docker run --network=isolated_network myapp
```

## 베스트 프랙티스

1. **공식 이미지 사용** - Docker Hub의 공식 이미지 선호
2. **멀티스테이지 빌드** - 최종 이미지 크기 최소화
3. **정기적 업데이트** - 베이스 이미지와 패키지 최신 상태 유지
4. **시크릿 관리** - 환경 변수나 Docker Secrets 사용
5. **로깅 및 모니터링** - 컨테이너 활동 추적

## 취약점 관리

```bash
# 정기적인 이미지 업데이트
docker pull node:18-alpine
docker build -t myapp:latest .

# 사용하지 않는 리소스 정리
docker system prune -a
```

## 결론

Docker 보안은 개발 초기 단계부터 고려해야 하며, 지속적인 모니터링과 업데이트가 필요합니다.
