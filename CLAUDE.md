# 클로드 수업 프로젝트 지침

## 필수 규칙

### 파일 수정 목록 명시
파일 수정 작업이 포함된 모든 응답의 **마지막**에 수정된 파일 목록을 반드시 나열한다.

형식:
> 수정된 파일: `파일명1` / `파일명2`

- 여러 파일을 동시에 수정할 때도 전부 나열
- 응답 본문 중간이 아닌 **맨 마지막**에 위치

### ver-badge 업데이트
HTML 파일 수정 시 해당 파일의 ver-badge 번호를 +1 올린다.
여러 파일을 같은 작업으로 동시에 수정할 때는 동일한 번호로 올린다.

---

## 프로젝트 개요

**제주고등학교 교원 AI 연수 — 2026.07.01~07.02 (2일 과정)**
강사: 강지애 / 대상: 교원 / 환경: Claude Pro 사전 가입 필수

---

## 파일 구성

| 파일 | 용도 | 현재 ver-badge |
|------|------|---------------|
| `index.html` | 홈 (교시별 카드 + 링크) | — |
| `one_v3.html` | 1일차 교육 자료 (1·2교시) | v3-6 |
| `two_v3.html` | 2일차 교육 자료 (3·4교시) | v3-10 |
| `prompt_v3.html` | 참고 프롬프트 예시집 | — |

---

## 섹션 구조

### one_v3.html (섹션 ID: sec0~sec10, TOC 11개 점)
- sec0: 히어로
- sec1: 시간표
- sec2: **강사 시연 — claude.ai 웹, 어디에 뭐가 있나?** (Projects/Artifacts/Code Execution/Memory 카드 4개)
- sec3: 강사 시연 — 클로드 인터페이스 화면 구성 이해
- sec4: 강의 — 핵심 기능 3가지
- sec5: 강의 — 프롬프트 작성법이 중요한 이유
- sec6: 강의 — 4가지 프롬프트 필수 요소
- sec7: 선생님 실습 — 교내 사업 계획서 초안 작성
- sec8: 강의 — GEAR 질문법
- sec9: 선생님 실습 — 실전 프롬프트 실습 3가지
- sec10: 마무리

### two_v3.html (섹션 ID: sec0~sec10, TOC 11개 점)
- sec0: 히어로
- sec1: 시간표
- sec2: 강사 시연 — 데스크탑 앱, 어디에 뭐가 있나?
- sec3: 강의 — Skills, 클로드 데스크탑이 달라지는 이유
- sec4: 강사 시연 — 교무 업무별 Skills 활용 가이드
- sec5: 선생님 실습 — 학부모 안내 문자 작성
- sec6: 선생님 실습 — 실제 교무 문서 파일 만들기
- sec7: 강사 시연 — MS Office 애드인 통합 활용
- sec8: 선생님 실습 — PPT 플러그인으로 교육 자료 작성
- sec9: 선생님 실습 — Excel 플러그인으로 성적·출결 처리
- sec10: 마무리

---

## 스타일 시스템

### 3단계 라벨 (h2 앞에 표시)
```css
.label-lecture  { background: #EDE9FE; color: #5B21B6; }  /* 강의 — 보라 */
.label-demo     { background: #D1FAE5; color: #065F46; }  /* 강사 시연 — 초록 */
.label-practice { background: #FEF3C7; color: #92400E; }  /* 선생님 실습 — 주황 */
```

### h2 제목 형식
`강사 시연 — 내용` / `강의 — 내용` / `선생님 실습 — 내용`

### 주요 CSS 클래스
- `.card`, `.card-grid-2` — 2열 카드 그리드
- `.interface-panel` — 인터페이스 설명 패널
- `.gear-example` — GEAR 예시 박스
- `.info-box` — 파란 안내 박스
- `.warn-box` — 주황 경고 박스
- 기본 font-size: 14.5px

---

## 주요 기술 정보

### Claude MS Office 애드인
- Excel/PPT 내 **추가 기능** 메뉴에서 직접 설치
- Claude.ai 웹에서 별도 커넥터/MCP 설정 불필요
- Word는 미지원 (Excel·PPT만 수업에서 다룸)
- 설치 후 Claude 계정으로 로그인 필요

### Claude 데스크탑 앱
- Chat / Claude Code / Cowork 세 개 탭 구성
- Skills 기능은 데스크탑 앱 전용

---

## 파일 크기 주의
`one_v3.html`, `two_v3.html`은 1,300~1,500줄 이상의 대형 파일.
Read 시 반드시 offset+limit 분할 읽기 사용. 전체 재작성 필요 시 Python 스크립트로 조립.
