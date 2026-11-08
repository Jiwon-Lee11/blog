# 📓 Jiwon Lee — Notes

연구 홈페이지(`Jiwon-Lee11.github.io`)와 별개로 운영하는 **공개 블로그**.
학회·논문·공부·장비·여행 기록을 올린다.

- 사이트: <https://jiwon-lee11.github.io/blog/>
- 연구 홈페이지: <https://jiwon-lee11.github.io/>

GitHub Pages 의 Jekyll 이 빌드한다. **로컬에 설치할 것이 없다** —
`.md` 파일을 하나 넣고 push 하면 1~2분 뒤 사이트에 뜬다.

---

## 글 올리는 법

### 1. 파일을 만든다

`_posts/` 안에 **`YYYY-MM-DD-영문제목.md`** 형식으로 만든다.
`_posts/TEMPLATE.md` 를 복사해서 쓰면 제일 빠르다.

```
_posts/2026-11-08-ajcpp-daegu.md
```

파일 이름의 날짜가 발행일이 되고, 주소는 이렇게 된다.

```
https://jiwon-lee11.github.io/blog/2026/11/08/ajcpp-daegu/
```

### 2. 맨 위에 front matter 를 쓴다

```yaml
---
title: "AJCPP 2027 다녀왔다"
date: 2026-11-08
cat: conference
tags: [AJCPP, 홀추력기]
event: "13th Asian Joint Conference on Propulsion and Power"
place: "대구, 대한민국"
dates: "2027. 3. 3 – 3. 6"
---
```

**`title` 과 `cat` 만 필수**다. 나머지는 없으면 그 줄을 지운다.
`event` / `place` / `dates` 는 글 머리에 회색 상자로 뜬다 — 학회나 여행 글에 쓰면 좋다.

### 3. 본문을 쓰고 push 한다

```bash
git add _posts/2026-11-08-ajcpp-daegu.md
git commit -m "학회: AJCPP 2027"
git push
```

1~2분 뒤에 반영된다. 빌드가 실패하면 GitHub 가 메일로 알려준다.

> 급하면 GitHub 웹에서 바로 쓸 수도 있다. 저장소 → `_posts` → **Add file** →
> **Create new file**. 휴대폰에서도 된다.

---

## `cat` 에 쓸 수 있는 값

`categories/` 폴더의 파일 이름과 같다. 주제를 늘리거나 이름을 바꾸려면
`_data/categories.yml` 을 고치고 `categories/` 에 같은 이름의 파일을 만든다.

| 묶음 | `cat` 값 |
|---|---|
| 🛰 연구 | `conference` · `papers` · `writing` · `ai` |
| 📚 공부 | `textbooks` · `courses` · `books` |
| 🎮 만들기 | `gamedev` |
| 🎒 장비 | `office` · `hiking` · `camping` · `fitness` |
| 🗺 기록 | `school` · `army` · `japan` · `abroad` |

`cat` 을 안 쓰면 주제 없는 글이 된다 — 홈의 "최근 글"과 "전체 글"에는 뜨지만
주제별 목록에는 안 들어간다.

---

## 사진

`assets/img/` 에 넣고 본문에서 이렇게 건다.

```markdown
![설명]({% raw %}{{ '/assets/img/raijin30.jpg' | relative_url }}{% endraw %})
```

**올리기 전에 긴 변 1600px 정도로 줄인다.** git 저장소는 한번 커지면
과거 커밋에 원본이 남아서 되돌리기 어렵다. 원본은 구글 드라이브에 두고
여기엔 줄인 것만 넣는 게 좋다.

---

## 구조

| 경로 | 내용 |
|---|---|
| `_config.yml` | 사이트 제목·주소·마크다운 설정 |
| `_data/categories.yml` | **주제 5묶음 16개 정의** (순서가 화면 순서) |
| `_posts/` | 글. 파일 이름이 `YYYY-MM-DD-제목.md` 여야 발행된다 |
| `_posts/TEMPLATE.md` | 복사용 템플릿 (날짜가 없어서 발행 안 됨) |
| `categories/*.md` | 주제별 목록 페이지. 내용 없이 front matter 만 |
| `_layouts/` | `default`(바깥틀) · `post`(글) · `category`(주제 목록) |
| `_includes/` | `head` · `nav` · `footer` · `post-card`(목록 한 줄) · `catname`(주제 이름) |
| `index.html` | 홈 — 주제 그리드 + 최근 8개 |
| `archive.md` | 전체 글, 연도별 |
| `assets/css/style.css` | 스타일. 색·폰트·다크모드는 연구 홈페이지와 맞췄다 |

## 메모

- 다크모드는 `localStorage` 의 `theme` 키를 쓴다. 연구 홈페이지와 **같은 출처**라
  한쪽에서 바꾸면 양쪽에 같이 적용된다.
- 주제를 추가할 때 `_data/categories.yml` 만 고치고 `categories/` 에 파일을
  안 만들면, 홈에서 카드는 보이지만 눌렀을 때 404 가 난다. 둘을 같이 고친다.
- 로컬에서 미리보기를 하려면 Ruby 와 Jekyll 이 필요하다
  (`gem install bundler jekyll` → `jekyll serve`). 없어도 글 쓰는 데는 지장이 없다.
