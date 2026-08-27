# papusKR

보안운영 · 침해대응 기록. <https://axplank.github.io>

## 구조

```
_config.yml          사이트 설정 · 네비게이션 · 카테고리 정의
_layouts/            default · page · post
_includes/           head · sidebar · rec(레코드 라인) · post-card
assets/css/main.css  전체 스타일 (색상은 :root 변수로 관리)
index.html           홈
blog.html            글 목록 + 카테고리 필터
portfolio.md         포트폴리오
about.md             소개
_posts/              글
```

## 글 쓰기

`_posts/YYYY-MM-DD-slug.md` 로 만들고 front matter를 채웁니다.

```yaml
---
title: "제목"
date: 2026-02-08
categories: [Detection, Sigma]
tags: [sigma, siem]
description: "목록 카드에 나오는 한 줄 요약."
---
```

- `categories[0]` 은 **Detection / Analysis / Operations / Notes** 중 하나만 사용합니다.
- `categories[1]` 은 자유롭게 씁니다. 블로그 페이지의 2단계 필터로 쓰입니다.
- 본문에 `# 제목` 을 다시 쓰지 않습니다. 레이아웃이 이미 출력합니다.

## 색 바꾸기

`assets/css/main.css` 최상단 `:root` 블록만 수정하면 사이트 전체에 반영됩니다.

## 로컬 실행 (선택)

```bash
bundle install
bundle exec jekyll serve
```
