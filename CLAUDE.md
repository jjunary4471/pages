# pages 레포 작업 규칙

GitHub Pages(https://jjunary4471.github.io/pages/)로 배포하는 정적 페이지 모음입니다. **공개 레포**입니다.

## 새 페이지를 추가하면 반드시 메인 목록 · 사이드바에 등록

- 메인 `index.html` 의 사이드바 목차는 본문 카드(`.group` → `ul` → `li > a.card`, `li > .subs a`)를 읽어 자동으로 만들어집니다. **카드를 등록하면 사이드바에도 들어갑니다.** 사이드바 HTML 은 직접 고치지 않습니다.
- 등록은 `site-index` 스킬의 스크립트로 합니다.
  ```bash
  python3 ~/.claude/skills/site-index/scripts/card.py upsert --group <그룹> --slug <slug> --href <dir>/ --title "<제목>" --desc "<설명>"
  python3 ~/.claude/skills/site-index/scripts/card.py sub --parent <부모 slug> --href <하위 경로>/ --title "<이름>"   # 하위 페이지
  python3 ~/.claude/skills/site-index/scripts/card.py check   # 커밋 전 누락 점검
  ```
- 가사(lyrics-page)·리딩(reading-page) 빌더는 카드를 자동으로 넣습니다. 로드맵 주차(cert-week-page)는 빌드 뒤 `sub` 로 붙입니다.

## 커밋

- 사용자가 작업 중인 미커밋 변경(예: `math/`, 메인 목록의 Math 카드)은 함께 커밋하지 않습니다. 메인 `index.html` 은 그 부분을 뺀 버전만 스테이징합니다(`git hash-object -w` + `git update-index --cacheinfo`).
- 개인정보(주소, 생년월일, 문서번호, 바코드 등)가 들어간 파일은 가린 뒤 올립니다.
- 커밋 메시지는 한국어로 씁니다.
