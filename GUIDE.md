# 제주고 클로드 교육 — HTML 자료 제작 지침

> 이 파일은 이 폴더의 HTML 교육 자료를 수정·추가할 때 참고하는 실무 지침서입니다.
> 새 채팅 시작 시 이 파일을 첨부하면 동일한 기준으로 작업을 이어갈 수 있습니다.

---

## 1. 연수 기본 정보

| 항목 | 내용 |
|------|------|
| 학교 | 제주고등학교 |
| 일정 | 2026년 07월 01일(화) ~ 07월 02일(수) |
| 구성 | 2일 과정 · 하루 2교시 · 총 4교시 · 200분 |
| 대상 | 고등학교 교원 |
| 전제 | Claude Pro 사전 가입 완료 상태 |
| 실습 비중 | 60% 이상 |

---

## 2. 파일 구조

```
260701 claude/
├── index.html     ← 랜딩 표지 (제주고 교육 표지 + 4교시 개요 카드)
├── one.html       ← 1일차 교육 자료 (1·2교시 전체 내용)
├── two.html       ← 2일차 교육 자료 (3·4교시 전체 내용)
├── prompt.html    ← 참고 프롬프트 예시집 (24개 카드 + 결과 예시 토글)
└── GUIDE.md       ← 이 파일 (제작 지침)
```

### 파일 역할 요약

- **index.html**: 진입점. 학교명·날짜·4교시 개요 카드 표시. 각 카드 클릭 시 해당 교시 페이지로 이동.
- **one.html**: 1일차 전체 내용. S0(히어로)~S9(마무리) 10개 섹션.
- **two.html**: 2일차 전체 내용. S0(히어로)~S9(마무리) 10개 섹션.
- **prompt.html**: 6개 카테고리 × 4개 프롬프트 = 24개 카드. 각 카드에 결과 예시 토글 포함.

---

## 3. 상단 내비게이션 규칙

모든 HTML 파일 상단에 동일한 `<nav class="top-nav">` 구조를 사용합니다.

```html
<nav class="top-nav">
  <div class="top-nav-inner">
    <span class="top-nav-logo">Claude AI 연수</span>
    <a href="index.html" class="top-nav-btn [active?]">홈</a>
    <a href="one.html"   class="top-nav-btn [active?]">1일차 교육</a>
    <a href="two.html"   class="top-nav-btn [active?]">2일차 교육</a>
    <a href="prompt.html" class="top-nav-btn [active?]">참고 프롬프트</a>
  </div>
</nav>
```

- 현재 페이지에 해당하는 버튼에만 `class="top-nav-btn active"` 추가
- nav는 `position: fixed; top: 3px; z-index: 200;` (진행 바 z-index: 300 아래)
- 진행 바는 `height: 3px; top: 0; z-index: 300;`으로 nav 위에 위치

### 각 파일별 active 버튼

| 파일 | active |
|------|--------|
| index.html | 홈 |
| one.html | 1일차 교육 |
| two.html | 2일차 교육 |
| prompt.html | 참고 프롬프트 |

---

## 4. 색상 토큰

### 1일차 (one.html, index.html)

```css
--navy: #1E2761
--blue: #3B5BDB
--purple: #7C3AED
--teal: #0891B2
--accent: #FCC419  /* 골드 강조 */
```

### 2일차 (two.html)

```css
--navy: #0F172A
--purple: #7C3AED
--cyan: #06B6D4
--accent: #FCC419
```

### 프롬프트 페이지 카테고리 색상 (prompt.html)

| 카테고리 | 색상 |
|---------|------|
| 행정 업무 | `#3B5BDB` (블루) |
| 수업 준비 | `#0891B2` (틸) |
| 평가·기록 | `#7C3AED` (퍼플) |
| 학생 생활 | `#EA580C` (오렌지) |
| 가정통신 | `#059669` (그린) |
| 연구·연수 | `#1E2761` (네이비) |

---

## 5. 하단 버튼 크기 통일 규칙

페이지 마무리 섹션의 버튼 쌍은 반드시 같은 크기로 맞춥니다.

```html
<a href="..." style="min-width:220px; text-align:center; ...">버튼 A</a>
<a href="..." style="min-width:220px; text-align:center; ...">버튼 B</a>
```

---

## 6. 프롬프트 결과 예시 토글 (prompt.html)

각 프롬프트 카드 아래에 아코디언 토글을 추가합니다.

```html
<!-- 프롬프트 박스 뒤에 추가 -->
<button class="result-toggle" onclick="toggleResult('r01', this)">
  결과 예시 보기 <span class="arrow">▼</span>
</button>
<div class="result-box" id="r01" style="display:none;">
  <div class="result-label">생성 결과 예시</div>
  <pre>[실제 결과 예시 텍스트]</pre>
</div>
```

JS 함수:
```javascript
function toggleResult(id, btn) {
  const box = document.getElementById(id);
  const isOpen = box.style.display === 'block';
  box.style.display = isOpen ? 'none' : 'block';
  btn.classList.toggle('open', !isOpen);
}
```

- 프롬프트 ID: `p01`~`p24`, 결과 ID: `r01`~`r24`
- 카테고리별 4개씩: p01~p04 행정, p05~p08 수업, p09~p12 평가, p13~p16 학생, p17~p20 가정통신, p21~p24 연구

---

## 7. 디자인 공통 규칙

- **폰트**: `'Noto Sans KR', 'Apple SD Gothic Neo', 'Malgun Gothic', sans-serif`
- **이모지 사용**: LibreOffice 렌더링 깨짐 우려가 없는 HTML에서는 사용 가능. PPT 제작 시에는 사용 금지.
- **★ 표시**: 시간 부족 시 생략 가능한 항목에 표시. 슬라이드/섹션 레이블에 명시.
- **copy-btn**: 다크 배경(`#0F172A`)의 프롬프트 박스 우상단. 클릭 시 "복사됨!" 2초 후 복원.
- **fade-in/fade-up**: `IntersectionObserver`로 스크롤 시 등장 애니메이션.
- **progress-bar**: 스크롤 진행률 표시. `top: 0; height: 3px; z-index: 300;`

### 폰트 크기 기준 (현행 — 2026-06-11 기준 +1px 적용 후)

| 용도 | 크기 |
|------|------|
| body 기본 | 16px |
| 본문 텍스트 (일반) | 16px |
| 카드 설명, 부가 정보 | 15px |
| 작은 레이블, 뱃지 | 14px |
| 보조 텍스트 | 13px ~ 13.5px |
| 최소 텍스트 (주석 등) | 11px ~ 12px |
| 섹션 타이틀 | 23px~ |
| 히어로/대형 제목 | 29px~ |

> **참고**: 향후 폰트 크기 조정 시 반드시 **내림차순** 순서로 replace_all 적용 (큰 값 먼저 → 작은 값). CSS 블록(`font-size: Xpx`)과 인라인(`font-size:Xpx`) 두 패턴 모두 처리 필요.

### 폰트 크기 증가 시 함께 보정해야 할 레이아웃 값

폰트를 일괄 증가할 경우 아래 값들을 **동시에** 조정해야 겹침/잘림이 발생하지 않습니다.

| 항목 | 파일 | 현행 값 | 보정 이유 |
|------|------|---------|---------|
| `timetable-row` 고정 열 | one.html, two.html | `96px 96px 1fr` | 배지 텍스트 공간 확보 |
| `timetable-row` 모바일 열 | one.html, two.html | `84px 84px 1fr` | 소형 화면 배지 여유 |
| `.card-subtitle margin-top` | index.html | `-2px` | 음수 마진 과다 시 제목과 겹침 |
| `.practice-num` 원형 크기 | one.html, two.html | `38×38px` | 폰트 대비 원 크기 여유 |
| `.step-num` 원형 크기 | two.html | `34×34px` | 동일 |
| `.tip-num` 원형 크기 | prompt.html | `36×36px` | 동일 |
| `.card-grid-4` gap | one.html | `16px` | 4열 좁은 카드 여백 |
| `.elem-body` 폰트 | one.html | `13px` | 4열 카드 내부 — 별도 다운 유지 |
| `.elem-example-box` 폰트 | one.html | `12px` | 동일 |
| `.card-title` line-height | prompt.html | `1.5` | 타이틀 줄 간격 충분히 유지 |

> **원칙**: 원형 배지(`.practice-num`, `.step-num`, `.tip-num`)는 `원 크기 ÷ 폰트 크기 ≥ 2.2` 비율을 유지합니다. 이 비율이 깨지면 원을 2px씩 키웁니다.

---

## 8. 교시별 실행 환경

| 교시 | 환경 | 비고 |
|------|------|------|
| 1교시 (1일차) | claude.ai 웹 브라우저 | 별도 설치 불필요 |
| 2교시 (1일차) | claude.ai 웹 브라우저 | 별도 설치 불필요 |
| 3교시 (2일차) | 클로드 데스크탑 앱 | **수업 전 사전 설치 필수** (Windows 10+ / macOS) |
| 4교시 (2일차) | MS Excel / PowerPoint 애드인 | [홈] → [추가기능] → Claude 검색 설치 |

---

## 9. 프롬프트 작성 규칙 (HTML 내 프롬프트 예시)

- 설명 텍스트: `~입니다 / ~합니다` 체
- 프롬프트 본문(따옴표 안): `~해 줘` 명령체
- 수정 가능 항목: `[대괄호]` 안에 표시
- 띄어쓰기: `작성해 줘 / 만들어 줘 / 써 줘` (붙여쓰기 금지)

---

## 10. 수정 이력

| 날짜 | 내용 |
|------|------|
| 2026-06-11 | index.html, two.html 생성 |
| 2026-06-11 | prompt.html 생성 (24개 프롬프트 카드) |
| 2026-06-11 | 3개 파일 상단 nav 바 추가 |
| 2026-06-11 | prompt.html 결과 예시 토글 24개 추가 |
| 2026-06-11 | two.html 하단 버튼 크기 통일 |
| 2026-06-11 | index.html → one.html 이름 변경 (1일차 교안) |
| 2026-06-11 | 새 index.html 생성 (제주고 교육 랜딩 표지) |
| 2026-06-11 | 전체 nav에 "홈" 버튼 추가, one.html 링크로 정리 |
| 2026-06-11 | 전체 폰트 크기 +1px 적용 (4개 파일: index, one, two, prompt) |
| 2026-06-11 | 폰트 증가 후 레이아웃 겹침 보정 (시간표 열 너비, 원형 배지 크기, card-subtitle 마진 등) |

---

*최종 업데이트: 2026-06-11*
