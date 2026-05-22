# Homepage — Working Notes

학술 개인 홈페이지 프로젝트. Jeheon Woo (AI Fellow, KIAS).

## Files in this folder
- `index.html` — 메인 페이지 (About + Publications)
- `cv.html` — CV 페이지 (전체 이력)
- (예정) `profile.jpg` — 프로필 사진

두 HTML은 서로 상대경로로 링크되어 있으므로 **항상 같은 폴더에 함께** 두어야 한다.

## Design / tech
- 폰트: Inter Tight (본문), Fraunces (강조 serif), JetBrains Mono (라벨) — Google Fonts CDN
- 아이콘: Font Awesome 6.5.1 — CDN
- 색상: 따뜻한 종이톤 배경 + deep green 액센트
- 외부 의존성은 전부 CDN. 빌드 과정 없음. 그냥 브라우저로 열면 됨.

## CV → PDF 방식
`homepage_cv.html`이 CV의 **유일한 원본**. PDF는 따로 관리하지 않는다.
페이지의 "Save as PDF" 버튼 = 브라우저 인쇄(`window.print()`). 인쇄 대화상자에서
"PDF로 저장" + "배경 그래픽 켜기"를 선택하면 화면과 동일한 PDF가 나온다.
정교한 `@media print` / `@page A4` 스타일이 이미 적용돼 있음.

## TODO (남은 작업)
1. **소셜 링크 채우기** — `index.html` 사이드바의 GitHub, LinkedIn URL이
   아직 루트 도메인(`https://github.com/` 등)으로 placeholder 상태.
   (Email, Google Scholar, ORCID는 실제 값으로 연결 완료.)
2. **논문 링크 채우기** — `index.html`의 doi/pdf/code/bibtex/openreview 버튼이
   `href="#"` placeholder. 실제 DOI·arXiv·GitHub URL로 교체.
3. **프로필 사진** — 현재 양쪽 다 "JW" 이니셜 박스.
   사진 추가 시: `<div class="portrait ...">JW</div>` (index) 와
   `<div class="cv-portrait ...">JW</div>` (cv) 를
   `<div class="portrait"><img src="profile.jpg" alt="Jeheon Woo"/></div>` 형태로 교체.

## 배포 (GitHub Pages)
파일명이 이미 `index.html`이므로 추가 작업 없이 그대로 올리면 된다.
루트 URL(`your-username.github.io/`)에서 index.html이 첫 화면으로 뜨고,
거기서 cv.html로 이동 가능.

레포 구조:
```
<your-username>.github.io/
├── index.html
├── cv.html
└── (선택) profile.jpg
```
