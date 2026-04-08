# seonang.github.io

미니멀 블로그 구조 메모.

## 구조
- 홈: `index.html`
- 글 모음: `blog.html` + `_posts/`
- 책: `books.html` + `_books/`
- 영화: `movies.html` + `_movies/`
- 공통 단일 글 레이아웃: `_layouts/entry.html`
- 공통 스타일: `assets/css/site.css`

## 작성 방식
각 문서는 Markdown으로 추가하고, `tags`를 달면 아카이브 측면 패널에서 태그 필터가 자동으로 생성됩니다.

### 글 모음 예시
```md
---
title: "제목"
description: "짧은 소개"
date: 2026-04-08 22:00:00 +0900
tags: [존재, 비즈니스, 일상관찰]
---

본문을 씁니다.
```

파일 경로 예시:
- `_posts/2026-04-08-my-post.md`

### 책 예시
```md
---
title: "린스타트업"
description: "왜 다시 읽을 가치가 있었는지"
author: "에릭 리스"
date: 2026-04-08
tags: [스타트업, 제품, 전략]
---

책에 대한 감상과 메모를 씁니다.
```

파일 경로 예시:
- `_books/lean-startup.md`

### 영화 예시
```md
---
title: "영화 제목"
description: "짧은 감상"
director: "감독 이름"
release_year: "2024"
date: 2026-04-08
tags: [고독, 장면, 대사]
---

영화에 대한 기록을 씁니다.
```

파일 경로 예시:
- `_movies/movie-title.md`

## 주의
- 기존 템플릿용 임시 글은 `placeholder: true`로 제외할 수 있습니다.
- 검색은 제목/설명/태그를 기준으로 동작합니다.
