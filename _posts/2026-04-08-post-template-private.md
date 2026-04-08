---
layout: entry
title: "포스트 작성 템플릿"
description: "포스트 작성용 기본 템플릿과 이미지 삽입 가이드"
date: 2026-04-08 22:00:00 +0900
archive_category: diary
tags: [템플릿, 작성가이드]
placeholder: false
---

이 파일은 **작성용 템플릿**입니다.

- 현재 상태에서는 `placeholder: true` 이므로 목록/검색에서 숨겨집니다.
- 실제 공개 글로 쓸 때는 `placeholder: true` 줄을 지우면 됩니다.
- 이 사이트는 정적 사이트라서 **완전 비공개 글**은 아니고, 현재 방식은 **목록/검색에서 숨기는 비공개 초안용**에 가깝습니다.

---

# 1. 기본 작성 방식

모든 글은 `_posts/` 폴더 안에서 작성합니다.

파일명 예시:

```text
_posts/2026-04-08-my-post.md
_posts/2026-04-08-lean-startup.md
_posts/2026-04-08-perfect-days.md

파일명은 보통 아래처럼 잡는 것을 권장합니다.

• 날짜-짧은영문슬러그.md
• 예: 2026-04-08-organization-speed.md

───

# 2. 가장 기본적인 템플릿

---
layout: entry
title: "글 제목"
description: "목록에서 보일 한 줄 소개"
date: 2026-04-08 22:00:00 +0900
archive_category: management
tags: [경영, 조직, 전략]
---

첫 문단을 씁니다.

## 소제목

본문을 계속 씁니다.

- 불릿 가능
- 일반 마크다운 가능

> 인용문도 가능
───

# 3. 분류(archive_category) 작성법

현재 사용하는 분류값은 아래 5개입니다.

• diary → 일기
• management → 경영
• philosophy → 철학
• book → 책
• movie → 영화

예시:

archive_category: diary
archive_category: management
archive_category: book
───

# 4. 태그(tags) 작성법

태그는 배열 형태로 작성합니다.

tags: [브랜딩, 전략, 포지셔닝]
또는 아래처럼 써도 됩니다.

tags:
  - 브랜딩
  - 전략
  - 포지셔닝
권장:

• 2~5개 정도
• 너무 긴 문장형 태그보다는 짧은 키워드형
• 목록에서는 앞의 몇 개만 보이고, 상세 글에서는 전부 보입니다.

───

# 5. 목록에서 실제로 보이는 항목

글을 클릭하기 전 목록 카드에서는 주로 아래 항목이 보입니다.

• 분류 라벨 (archive_category)
• 제목 (title)
• 설명 (description)
• 날짜 (date)
• 태그 일부 (tags)

즉, 미리보기 퀄리티는 사실상 아래 4개가 결정합니다.

• title
• description
• archive_category
• tags

특히 description을 꼭 쓰는 것을 추천합니다.

───

# 6. 책 포스트 템플릿

---
layout: entry
title: "린스타트업"
description: "다시 읽어보니 제품보다 학습 속도에 대한 책이었다."
date: 2026-04-08 22:00:00 +0900
archive_category: book
author: "에릭 리스"
translator: "옮긴이 이름"
publisher: "출판사 이름"
tags: [스타트업, 제품, 학습]
---

책에 대한 메모를 씁니다.
선택 가능 메타데이터:

• author
• translator
• publisher

───

# 7. 영화 포스트 템플릿

---
layout: entry
title: "퍼펙트 데이즈"
description: "고독과 반복이 이상하게 따뜻하게 느껴졌던 영화."
date: 2026-04-08 22:00:00 +0900
archive_category: movie
director: "빔 벤더스"
release_year: "2023"
rating: "4.7/5"
tags: [영화, 고독, 장면]
---

영화에 대한 기록을 씁니다.
선택 가능 메타데이터:

• director
• release_year
• rating

───

# 8. 사진 넣는 방법

이 블로그에서 사진을 넣으려면, 이미지를 먼저 repo 안의 assets/images/ 아래에 넣고 Markdown에서 불러오면 됩니다.

권장 경로 예시:

assets/images/posts/2026-04-08-organization-speed/cover.jpg
assets/images/posts/2026-04-08-organization-speed/01.jpg
assets/images/posts/2026-04-08-organization-speed/02.jpg
Markdown에서는 이렇게 넣습니다.

\![이미지 설명](/assets/images/posts/2026-04-08-organization-speed/cover.jpg)
문단 사이 예시:

앞 문단입니다.

\![조직 구조 메모](/assets/images/posts/2026-04-08-organization-speed/01.jpg)

다음 문단입니다.
이미지 작성 팁:

• 파일명은 영문/숫자/하이픈 위주 추천
• 한 포스트당 이미지 폴더를 따로 파면 관리가 편함
• 대표 이미지가 있으면 cover.jpg처럼 통일하면 찾기 쉬움
• 너무 큰 원본은 웹에서 느릴 수 있으니 적당히 줄여서 업로드 추천

───

# 9. 공개 전 체크리스트

공개 전에 아래만 확인하면 됩니다.

• 제목이 명확한가
• description이 있는가
• archive_category가 맞는가
• tags가 너무 많지 않은가
• placeholder: true를 지웠는가
• 이미지 경로가 실제 파일 경로와 일치하는가

───

추가로 이미지 쪽은 이미 `assets/images/` 폴더가 있어서 바로 써도 됩니다.
