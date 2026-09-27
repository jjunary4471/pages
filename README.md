# pages

GitHub Pages로 배포하는 정적 페이지 모음입니다.

## 구조

```
index.html                     # 페이지 목록 (TOEIC / Lyrics 그룹)
lyrics/<slug>/index.html       # 팝송 가사 페이지 (lyrics-page 스킬)
toeic/index.html               # 토익 단어 학습 앱
toeic/data/words.json          # 단어 데이터 (toeic-words 스킬로 추가)
```

## 페이지 추가 방법

1. 주제별 폴더 아래에 `<slug>/index.html` 을 만듭니다. (예: `lyrics/<slug>/index.html`)
2. `index.html` 의 목록에 카드 하나를 추가합니다.
3. `main` 브랜치에 푸시하면 자동으로 배포됩니다.
