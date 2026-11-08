<!--
  글 템플릿.

  이 파일은 이름이 `YYYY-MM-DD-제목.md` 형식이 아니라서 사이트에 올라가지 않는다.
  새 글을 쓸 때 이 파일을 복사해서 `_posts/2026-11-08-ajcpp-daegu.md` 처럼
  날짜를 앞에 붙여 저장하면 된다.

  파일 이름의 날짜가 글의 발행일이 되고, 주소는
  https://jiwon-lee11.github.io/blog/2026/11/08/ajcpp-daegu/ 가 된다.
  파일 이름은 영문·숫자·하이픈으로 쓴다 (한글도 되지만 주소가 길어진다).

  아래 `---` 사이가 front matter. title 과 cat 만 필수.
-->

---
title: "여기에 글 제목"
date: 2026-11-08
cat: conference

# ↓ 여기부터는 다 선택 사항. 안 쓸 줄은 지우면 된다.
tags: [태그1, 태그2]
event: "13th Asian Joint Conference on Propulsion and Power"
place: "대구, 대한민국"
dates: "2027. 3. 3 – 3. 6"
---

첫 문단은 목록에 요약으로 뜬다. 한두 문장으로 글 전체를 말해 두면 좋다.

## 소제목

본문. **굵게**, *기울임*, `코드`, [링크](https://example.com) 다 된다.

- 목록
- 목록
  - 들여쓴 목록

> 인용문

| 표 | 도 | 된다 |
|---|---|---|
| 가 | 나 | 다 |

사진은 `assets/img/` 에 넣고 이렇게 건다. 올리기 전에 긴 변 1600px 정도로
줄여야 저장소가 무거워지지 않는다.

![설명]({{ '/assets/img/파일이름.jpg' | relative_url }})

각주도 된다.[^1]

[^1]: 각주 내용은 글 맨 아래에 모인다.

```python
# 코드 블록
print("색칠까지 된다")
```

<!--
  cat 에 쓸 수 있는 값 (categories/ 폴더의 파일 이름과 같다):

  연구    conference  papers  writing  ai
  공부    textbooks   courses books
  만들기  gamedev
  장비    office      hiking  camping  fitness
  기록    school      army    japan    abroad
-->
