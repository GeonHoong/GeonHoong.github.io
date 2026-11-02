# GeonHong Kim — Personal Site

## 올리는 방법 (GitHub Pages)
1. GitHub에서 새 저장소 생성 → 이름을 정확히 `본인아이디.github.io` 로.
2. 이 폴더의 파일 전부(`index.html`, `style.css`, `assets/`)를 저장소에 업로드 (Add file → Upload files, 드래그 앤 드롭).
3. 저장소 **Settings → Pages → Branch: main / (root)** → Save.
4. 1~2분 뒤 `https://본인아이디.github.io` 접속.

## 채워야 할 것 (페이지에서 주황 점선 박스 = TODO)
- `assets/profile.jpg` — 프로필 사진 (정사각형 권장)
- `assets/GeonHong_Kim_CV.pdf` — CV PDF
- `index.html` 에서 `[TODO]` 검색 → GitHub/Scholar/LinkedIn 링크, 졸업 예정, 자기소개, 지도교수 링크
- 프로젝트 이미지: `assets/projects/` 에 넣고 각 카드의 `<div class="card-img todo">…</div>` 를 `<div class="card-img"><img src="assets/projects/파일명" alt=""></div>` 로 교체
- 논문 대표 그림: `assets/pubs/` 동일 방식
- Gallery: 필요 없으면 `<section id="gallery">` 블록 삭제

내용을 채운 뒤 `class="todo"` 를 지우면 점선 테두리가 사라집니다.

## 색/폰트 바꾸기
`style.css` 맨 위 `:root` 변수(`--accent` 등)만 수정하면 됩니다. 다크모드는 자동 지원.
