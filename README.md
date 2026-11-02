# GeonHong Kim — 개인 포트폴리오 사이트

사이트 주소: https://geonhoong.github.io

## 파일 구성

```
index.html      ← 모든 내용(글, 링크, 이미지 경로). 수정은 대부분 이 파일에서
style.css       ← 색상·글꼴·레이아웃. 맨 위 :root 변수만 바꾸면 전체 색이 바뀜
assets/
  profile.jpg           ← 프로필 사진 (넣기만 하면 자동 표시)
  GeonHong_Kim_CV.pdf   ← "Curriculum Vitae" 버튼이 여는 파일
  research/             ← Featured Research 이미지
  projects/             ← Projects 카드 이미지
  pubs/                 ← 논문/포스터 썸네일
```

---

## 1. GitHub에서 글 수정하기

1. 저장소에서 `index.html` 클릭
2. 오른쪽 위 연필 아이콘(**Edit this file**) 클릭
3. 내용 수정
4. 오른쪽 위 초록 **Commit changes…** → 다시 **Commit changes**
5. 1~2분 뒤 사이트 새로고침 (안 바뀌면 `Ctrl + Shift + R`)

파일 전체를 교체할 때는 **Add file → Upload files** 로 같은 이름의 파일을 올리면 덮어써집니다.

`Ctrl + F` 로 `TODO` 를 검색하면 아직 채워야 할 곳이 전부 나옵니다.
채운 뒤에는 `class="todo"` 를 지워야 갈색 글씨가 사라집니다.

```html
<!-- 전 -->
<p class="todo">[TODO] 한두 문장 추가 …</p>
<!-- 후 -->
<p>저는 대학원 진학을 준비하고 있으며 …</p>
```

---

## 2. 사진 넣기

### 2-1. 사진 파일 올리기

**방법 A (쉬움) — 폴더째 드래그**
1. 컴퓨터에서 `assets` 폴더를 만들고 그 안에 사진을 넣음 (예: `assets/profile.jpg`, `assets/projects/glove.jpg`)
2. 저장소 → **Add file → Upload files**
3. `assets` **폴더 자체**를 회색 영역에 드래그 앤 드롭 (파일 선택 창으로는 폴더가 안 되고, 드래그만 됨. Chrome/Edge)
4. 목록에 `assets/projects/glove.jpg` 처럼 경로가 뜨는지 확인 → **Commit changes**

**방법 B — 폴더 안으로 들어가서 업로드**
1. 저장소에서 `assets` → `projects` 폴더 클릭
2. **Add file → Upload files** → 사진 드래그 → **Commit changes**
3. 아직 없는 폴더는 **Add file → Create new file** 에서 이름을 `assets/pubs/.gitkeep` 처럼 치면(슬래시 입력 시 폴더 생성) 빈 내용으로 Commit → 폴더 생김

권장 크기: 프로필 600×600 이상(정사각형), 프로젝트·연구 이미지 1200×900 정도. 파일명은 영문·소문자·공백 없이.

### 2-2. index.html 에 연결하기

**프로필 사진** — `assets/profile.jpg` 로 올리면 끝. 코드 수정 없음.

**나머지** — 회색 박스(`<div class="ph …">`)를 `<img>` 로 바꿉니다.

| 위치 | 바꾸기 전 | 바꾼 후 |
|---|---|---|
| Featured Research | `<div class="ph wide"><span>Image / GIF …</span></div>` | `<img src="assets/research/cable-robot.jpg" alt="">` |
| Projects 카드 | `<div class="ph card-img"><span>Image / GIF</span></div>` | `<img src="assets/projects/glove.jpg" alt="">` |
| Publications 썸네일 | `<div class="ph thumb"><span>Figure</span></div>` | `<img src="assets/pubs/ksme-a.png" alt="">` |
| Gallery | `<div class="ph"><span>Photo</span></div>` | `<img src="assets/gallery/lab1.jpg" alt="">` |

`<div class="ph …"> … </div>` 한 줄을 통째로 `<img …>` 한 줄로 교체하면 됩니다. GIF 도 같은 방식.

---

## 3. 자주 하는 수정

**News 추가** — `<ul class="news">` 안 맨 위에 한 줄 복사·추가
```html
<li><time>Dec 2026</time><div>내용</div></li>
```

**프로젝트 추가** — `<article class="card"> … </article>` 블록 하나를 복사해서 붙이고 내용 수정.
Research & Development / Competitions 중 맞는 `<div class="grid">` 안에 넣기.

**논문 추가** — `<div class="pub"> … </div>` 블록 복사. 연도가 바뀌면 위에 `<h3 class="group">2027</h3>` 추가.

**링크 채우기** — `href="#"` 로 되어 있는 곳이 아직 빈 링크. 주소를 넣거나, 필요 없으면 그 `<a>` 줄 삭제.
- LinkedIn / Scholar 버튼: Hero 의 `.actions`
- Paper / Poster / Video 버튼: 각 연구·논문의 `<a class="chip" href="#">`

**섹션 삭제** — 예: Gallery 가 필요 없으면 `<section id="gallery"> … </section>` 블록 삭제. 상단 nav 에 링크가 있다면 그 `<a>` 도 같이 삭제.

**색 바꾸기** — `style.css` 맨 위
```css
--accent: #2f8f4e;       /* 메인 포인트 */
--accent-dark: #22703c;  /* hover, 진한 글자 */
--accent-soft: #e6f4ea;  /* 태그 배경 */
--lime: #a8d96c;         /* 수상 배지 */
```

**"Last updated" 날짜** — `index.html` 맨 아래 `<footer>` 에서 수정.

---

## 4. 처음 배포할 때 (한 번만)

1. 저장소 이름이 아이디와 같은 `GeonHoong.github.io` 인지 확인
2. **Settings → Pages → Branch: main / (root) → Save**
3. 1~2분 뒤 https://geonhoong.github.io 접속
