# seonang.github.io

미니멀 블로그 구조 메모.

## 구조
- 홈: `index.html` (`/`)
- 블로그 메인: `blog.html` (`/blog/`)
- 검색: `search.html` (`/search/?q=검색어`)
- 카테고리: `category/<카테고리>/index.html`
- 책: `books.html` (`/books/`)
- 영화: `movies.html` (`/movies/`)
- 공통 아카이브 UI: `_includes/archive-shell.html`
- 공통 단일 글 레이아웃: `_layouts/entry.html`
- 공통 스타일: `assets/css/site.css`

## 작성 방식
모든 문서는 `_posts/` 안의 Markdown 파일로 추가합니다.
분류는 폴더가 아니라 front matter의 `archive_category`로 구분합니다.

태그는 `tags`를 달면 아카이브 측면 패널과 검색에서 자동 반영됩니다.

## 분류값
`archive_category` 값은 아래 중 하나를 사용합니다.

- `diary`
- `management`
- `philosophy`
- `book`
- `movie`

## 파일 경로 규칙
모든 글은 `_posts/` 안에서만 관리합니다.

파일명 예시:
- `_posts/2026-04-08-my-post.md`
- `_posts/2026-04-08-lean-startup.md`
- `_posts/2026-04-08-perfect-days.md`

## 일반 글 예시
```md
---
title: "제목"
description: "짧은 소개"
date: 2026-04-08 22:00:00 +0900
archive_category: management
tags: [경영, 전략, 조직]
---
> Seonang Bot:
{% assign derived_section_label = '철학' %}
    {% assign derived_section_url = '/category/철학/' %}
  {% elsif page.archive_category == 'diary' %}
    {% assign derived_section_label = '일기' %}
    {% assign derived_section_url = '/category/일기/' %}
  {% else %}
    {% assign derived_section_label = '글 모음' %}
    {% assign derived_section_url = '/blog/' %}
  {% endif %}
{% endif %}

<section class="entry-page">
  <div class="entry-wrap">
    <a class="entry-back" href="{{ derived_section_url | relative_url }}">← {{ derived_section_label }}</a>

    <header class="entry-header">
      <p class="eyebrow">{{ derived_section_label }}</p>
      <h1 class="entry-title">{{ page.title }}</h1>
      {% if page.description %}
        <p class="entry-description">{{ page.description }}</p>
      {% endif %}

      <div class="entry-meta">
        {% if page.date %}<span>{{ page.date | date: "%Y.%m.%d" }}</span>{% endif %}
        {% if page.author %}<span>저자 {{ page.author }}</span>{% endif %}
        {% if page.translator %}<span>옮긴이 {{ page.translator }}</span>{% endif %}
        {% if page.publisher %}<span>{{ page.publisher }}</span>{% endif %}
        {% if page.director %}<span>감독 {{ page.director }}</span>{% endif %}
        {% if page.release_year %}<span>{{ page.release_year }}</span>{% endif %}
        {% if page.rating %}<span>{{ page.rating }}</span>{% endif %}
      </div>

      {% if page.tags and page.tags.size > 0 %}
        <div class="tag-list">
          {% for tag in page.tags %}
            <span class="tag-chip">#{{ tag }}</span>
          {% endfor %}
        </div>
      {% endif %}
    </header>

    <article class="entry-content prose">
      {{ content }}
    </article>
  </div>
</section>

───

4) README.md

# seonang.github.io

미니멀 블로그 구조 메모.

## 구조
- 홈: `index.html` (`/`)
- 블로그 메인: `blog.html` (`/blog/`)
- 검색: `search.html` (`/search/?q=검색어`)
- 카테고리: `category/<카테고리>/index.html`
- 책: `books.html` (`/books/`)
- 영화: `movies.html` (`/movies/`)
- 공통 아카이브 UI: `_includes/archive-shell.html`
- 공통 단일 글 레이아웃: `_layouts/entry.html`
- 공통 스타일: `assets/css/site.css`

## 작성 방식
모든 문서는 `_posts/` 안의 Markdown 파일로 추가합니다.
분류는 폴더가 아니라 front matter의 `archive_category`로 구분합니다.

태그는 `tags`를 달면 아카이브 측면 패널과 검색에서 자동 반영됩니다.

## 분류값
`archive_category` 값은 아래 중 하나를 사용합니다.

- `diary`
- `management`
- `philosophy`
- `book`
- `movie`

## 파일 경로 규칙
모든 글은 `_posts/` 안에서만 관리합니다.

파일명 예시:
- `_posts/2026-04-08-my-post.md`
- `_posts/2026-04-08-lean-startup.md`
- `_posts/2026-04-08-perfect-days.md`

## 일반 글 예시
```md
---
title: "제목"
description: "짧은 소개"
date: 2026-04-08 22:00:00 +0900
archive_category: management
tags: [경영, 전략, 조직]
---

본문을 씁니다.

책 글 예시

---
title: "린스타트업"
description: "왜 다시 읽을 가치가 있었는지"
date: 2026-04-08 22:00:00 +0900
archive_category: book
author: "에릭 리스"
tags: [스타트업, 제품, 전략]
---

책에 대한 감상과 메모를 씁니다.

영화 글 예시

---
title: "영화 제목"
description: "짧은 감상"
date: 2026-04-08 22:00:00 +0900
archive_category: movie
director: "감독 이름"
release_year: "2024"
tags: [고독, 장면, 대사]
---

영화에 대한 기록을 씁니다.

목록에서 보이는 정보

아카이브 목록(홈/블로그/카테고리/검색)에서는 아래 정보가 보입니다.

• 분류 라벨
• title
• description
  • 없으면 본문 excerpt 일부 사용
• date
• 태그 최대 3개

상세 페이지에서 보이는 정보

상세 페이지에서는 아래 정보가 사용됩니다.

• title
• description
• date
• tags
• 책 메타데이터: author, translator, publisher
• 영화 메타데이터: director, release_year, rating

주의

• 기존 템플릿용 임시 글은 placeholder: true로 제외할 수 있습니다.
• 검색은 제목/설명/저자/감독/본문 일부/태그를 기준으로 동작합니다.


---

## 삭제할 파일
이건 내용 복붙이 아니라 **삭제**입니다.

> Seonang Bot:
- `_books/.gitkeep`
- `_movies/.gitkeep`

그리고 삭제 후 빈 폴더도 정리:
- `_books/`
- `_movies/`

---

## 운영 방식 요약
앞으로 대표님은 이렇게만 쓰면 됩니다.

예:
```md
_posts/2026-04-08-lean-startup.md

---
title: "린스타트업"
description: "다시 읽어보니 제품보다 학습 속도에 대한 책이었다."
date: 2026-04-08 22:00:00 +0900
archive_category: book
author: "에릭 리스"
tags: [스타트업, 제품, 학습]
---

본문...본문을 씁니다.
