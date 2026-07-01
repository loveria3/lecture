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

**실제 배포 사이트(GitHub Pages): https://loveria3.github.io/lecture/index.html**
`index.html`이 실제로 연결하는 파일은 `v4` 버전이다. **`v3` 파일들은 더 이상 index.html에서 연결되지 않는 이전 버전(백업)** — 신규 작업은 반드시 `v4` 파일에 적용한다.

| 파일 | 용도 | 현재 ver-badge |
|------|------|---------------|
| `index.html` | 홈 (교시별 카드 + 링크, one_v4/two_v4/prompt_v4로 연결) | — |
| `one_v4.html` | 1일차 교육 자료 (1·2교시) — **현재 연결 파일** | v4-16 |
| `two_v4.html` | 2일차 교육 자료 (3·4교시) — **현재 연결 파일** | v4-18 |
| `prompt_v4.html` | 참고 프롬프트 예시집 — **현재 연결 파일** | v4-1 |
| `one_v3.html` / `two_v3.html` / `prompt_v3.html` | 이전 버전 (index.html 미연결, 참고용) | v3-6 / v3-10 / — |
| `desktop_install.html` | 데스크탑 앱 설치 가이드 — hwpx.html처럼 새 탭으로 열리는 독립 실습 페이지. two_v4.html sec2 카드에서 연결 | ver-badge 없음 |

> `desktop_install.html`은 노트북 연결이 어려운 경우 현장 PC(강사 데스크탑 등)에서도 동일하게 설치할 수 있도록 안내하는 페이지. 설치 단계 스크린샷(다운로드/설치/로그인 화면)은 아직 없어 플레이스홀더로 남겨둠 — 확보되면 hwpx.html의 before/after 이미지 삽입 패턴과 동일하게 교체.

---

## 섹션 구조

> 아래는 현재 연결 파일인 `v4` 기준. `v3` 구조는 이 문서 하단 "v3 (이전 버전) 섹션 구조 — 참고용" 참조.

### one_v4.html (섹션 ID: sec0~sec13, TOC 14개 점)
- sec0: 히어로
- sec1: 1일차 시간표
- sec2: 강의 — claude.ai 웹, 어디에 뭐가 있나?
- sec3: 강의 — 클로드 인터페이스 화면 구성 이해
- sec4: 강의 — 핵심 기능 3가지
- sec5: 강의 — 프롬프트 작성법이 중요한 이유
- sec6: 강의 — GEAR 질문법
- sec7: 강사 시연 — GEAR로 완성한 프롬프트
- sec8: 선생님 실습 — 학부모 안내 문자 작성
- sec9: 선생님 실습 — 교내 사업 계획서 초안 작성
- sec10: 선생님 실습 — 실전 프롬프트 실습 3가지
- sec11: 심화 활용 — 반 단위 행동특성 일괄 생성
- sec12: ★ 보너스 실습 — 카카오톡 나와의 채팅 연결해 보기
- sec13: 마무리 (closing)

### two_v4.html (섹션 ID: sec0~sec4, sec6~sec10 — **sec5는 결번**, TOC 10개 점)
> sec4에 강사 시연과 선생님 실습을 통합하면서 구 sec5(선생님 실습 — Skills 활용·실제 교무 문서 파일 제작)를 삭제했다. 뒤쪽 섹션들은 id를 그대로 유지하고 화면 표시 번호(h2 텍스트)만 1씩 당겨서 sec5 id는 결번으로 남아있다. index.html의 `two_v4.html#sec6`(한글 실습 바로가기) 앵커는 영향 없음. `sections` JS 배열과 TOC 점 개수도 10개로 수정됨.
- sec0: 히어로
- sec1: 2일차 시간표
- sec2: 강사 시연 — 데스크탑 앱, 어디에 뭐가 있나? (Skills 사용 전 필수 설정: Code Execution 켜기 포함 / 데스크탑 설치 가이드 링크 카드 / 다같이 폴더 연결해보기 카드 / 지침(CLAUDE.md·Custom Instructions) 만들어보기 카드 + 복사용 지침 예시)
- sec3: 강의 — Skills vs MS Office 애드인, 언제 뭘 쓰나?
- sec4 (표시 "4."): 강사 시연 — 교무 업무별 Skills 다같이 실습 (Word/Excel/PPT/PDF 4개 스킬 시연+실습 통합, 미설치자 안내 박스 + 산출물 셀프체크 포함)
- sec6 (표시 "5."): 선생님 실습 — 한글(HWPX) 스킬로 공문서 작성해보기 (`hwpx.html` 새 탭 연결)
- sec7 (표시 "6."): 강사 시연 — MS Office 애드인 통합 활용
- sec8 (표시 "7."): 선생님 실습 — PPT 플러그인으로 교육 자료 작성
- sec9 (표시 "8."): 선생님 실습 — Excel 플러그인으로 성적·출결 처리
- sec10: 마무리 (closing)

---

## v3 (이전 버전) 섹션 구조 — 참고용

### one_v3.html (섹션 ID: sec0~sec10, TOC 11개 점)
- sec0: 히어로 / sec1: 시간표 / sec2: 강사 시연 — claude.ai 웹, 어디에 뭐가 있나? / sec3: 강사 시연 — 클로드 인터페이스 화면 구성 이해 / sec4: 강의 — 핵심 기능 3가지 / sec5: 강의 — 프롬프트 작성법이 중요한 이유 / sec6: 강의 — 4가지 프롬프트 필수 요소 / sec7: 선생님 실습 — 교내 사업 계획서 초안 작성 / sec8: 강의 — GEAR 질문법 / sec9: 선생님 실습 — 실전 프롬프트 실습 3가지 / sec10: 마무리

### two_v3.html (섹션 ID: sec0~sec10, TOC 11개 점)
- sec0: 히어로 / sec1: 시간표 / sec2: 강사 시연 — 데스크탑 앱, 어디에 뭐가 있나? / sec3: 강의 — Skills, 클로드 데스크탑이 달라지는 이유 / sec4: 강사 시연 — 교무 업무별 Skills 활용 가이드 / sec5: 선생님 실습 — 학부모 안내 문자 작성 / sec6: 선생님 실습 — 실제 교무 문서 파일 만들기 / sec7: 강사 시연 — MS Office 애드인 통합 활용 / sec8: 선생님 실습 — PPT 플러그인으로 교육 자료 작성 / sec9: 선생님 실습 — Excel 플러그인으로 성적·출결 처리 / sec10: 마무리

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
`one_v4.html`(1,772줄), `two_v4.html`(1,164줄), `prompt_v4.html`(1,475줄) 모두 1,100줄 이상의 대형 파일.
Read 시 반드시 offset+limit 분할 읽기 사용. 전체 재작성 필요 시 Python 스크립트로 조립.

---

## hwpx.html — 샘플 Before/After 이미지 삽입 작업

### 개요
`hwpx.html`은 193,000자 이상의 대형 파일(Base64 이미지 내장). 반드시 **Python 스크립트**로 수정한다. Edit 도구 직접 사용 불가(파일 크기 초과 오류).

### 완료된 작업
- **샘플 1** (업무 보고서): `hwpx/sample_report_before.png` / `hwpx/sample_report_after.png` ✅
- 라이트박스(클릭 시 크게 보기) 기능도 삽입 완료 ✅

### 남은 작업: 샘플 2·3·4
이미지는 `hwpx/` 폴더에 `*_before.png` / `*_after.png` 형태로 저장 예정.

| 샘플 | 제목 | 예상 파일명 (협의 후 확정) |
|------|------|--------------------------|
| 샘플 2 | 행사 계획서 작성 | `hwpx/sample_event_before.png` / `hwpx/sample_event_after.png` |
| 샘플 3 | 이미지 → 한글 문서 변환 | `hwpx/sample_letter_before.png` / `hwpx/sample_letter_after.png` |
| 샘플 4 | DOCX → 한글 문서 변환 | `hwpx/sample_lesson_before.png` / `hwpx/sample_lesson_after.png` |

> 실제 파일명은 작업 시 사용자에게 확인한다.

### 각 샘플의 플레이스홀더 고유 식별 문자열

**샘플 2** — 아래 텍스트 바로 뒤의 `result-area` 블록을 교체:
```
공문서\n격식체로 작성해줘.</div>\n            <div class="result-area">
```

**샘플 3** — 아래 텍스트 바로 뒤의 `result-area` 블록을 교체:
```
공문서 형식에 맞게 정리해줘.</div>\n            <div class="result-area">
```

**샘플 4** — 아래 텍스트 바로 뒤의 `result-area` 블록을 교체:
```
제목·단락·표를 정돈해서 완성해줘.</div>\n            <div class="result-area">
```

### 교체 템플릿 (Python 스크립트 사용)

```python
import re

content = open('/sessions/.../lecture/hwpx.html', encoding='utf-8').read()

PLACEHOLDER = '''<div class="result-area">
              <div class="result-area-header">
                <span>📄</span> 결과 미리보기
              </div>
              <div class="result-placeholder">
                <div class="ph-icon">🖼️</div>
                <p>결과 이미지를 여기에 넣어주세요</p>
                <p style="font-size:12px; opacity:0.7">완성된 문서 스크린샷 업로드 예정</p>
              </div>
            </div>'''

def make_before_after(before_src, after_src):
    return f'''<div class="result-area">
              <div class="result-area-header">
                <span>📄</span> 결과 미리보기 — Before / After
              </div>
              <div style="display:grid;grid-template-columns:1fr 1fr;gap:12px;padding:16px;">
                <div>
                  <div style="text-align:center;font-size:12px;font-weight:700;color:#6B7280;letter-spacing:.06em;margin-bottom:8px;">
                    ⬅ BEFORE &nbsp;빈 양식 파일
                  </div>
                  <img src="{before_src}" alt="작성 전" onclick="openLightbox(this.src)" style="width:100%;border-radius:8px;border:2px solid #E5E7EB;box-shadow:0 2px 8px rgba(0,0,0,.10);cursor:zoom-in;">
                </div>
                <div>
                  <div style="text-align:center;font-size:12px;font-weight:700;color:#5B21B6;letter-spacing:.06em;margin-bottom:8px;">
                    AFTER ➡ Claude가 완성한 문서
                  </div>
                  <img src="{after_src}" alt="완성된 문서" onclick="openLightbox(this.src)" style="width:100%;border-radius:8px;border:2px solid #8B5CF6;box-shadow:0 2px 8px rgba(91,33,182,.15);cursor:zoom-in;">
                </div>
              </div>
            </div>'''

# 샘플별로 replace (각각 1회씩, 앞 텍스트로 고유 식별)
content = content.replace(
    '공문서\n격식체로 작성해줘.</div>\n            ' + PLACEHOLDER,
    '공문서\n격식체로 작성해줘.</div>\n            ' + make_before_after('hwpx/sample_event_before.png', 'hwpx/sample_event_after.png'),
    1
)
# 샘플 3, 4도 동일 패턴으로 추가

open('/sessions/.../lecture/hwpx.html', 'w', encoding='utf-8').write(content)
```

### 라이트박스
이미 삽입 완료. 추가 샘플 이미지에는 `onclick="openLightbox(this.src)"` + `cursor:zoom-in` 만 추가하면 자동 작동.
