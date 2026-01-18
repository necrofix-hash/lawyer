# RIGHTWAY 디자인 관리 가이드

이 문서는 RIGHTWAY 법률사무소 홈페이지의 디자인을 관리하고 수정하는 방법을 안내합니다.

---

## 목차

1. [파일 구조](#파일-구조)
2. [색상 변경](#색상-변경)
3. [폰트 변경](#폰트-변경)
4. [간격/여백 조정](#간격여백-조정)
5. [컴포넌트별 수정 위치](#컴포넌트별-수정-위치)
6. [반응형 디자인](#반응형-디자인)
7. [애니메이션](#애니메이션)
8. [아이콘 수정](#아이콘-수정)
9. [실전 예제](#실전-예제)

---

## 파일 구조

```
lawyer/
├── index.html          # 메인 페이지
├── about.html          # 사무소 소개
├── practice.html       # 업무 분야
├── team.html           # 변호사 소개
├── cases.html          # 성공 사례
├── contact.html        # 상담 문의
├── css/
│   └── style.css       # ⭐ 모든 스타일 관리
├── js/
│   └── main.js         # 인터랙션 (네비게이션, 폼, 필터)
└── CLAUDE.md           # 브랜드 가이드라인
```

**핵심 파일:** `css/style.css` - 모든 디자인은 이 파일에서 관리됩니다.

---

## 색상 변경

### CSS 변수 위치: `css/style.css` 6~29번 줄

```css
:root {
  /* ========== PRIMARY - 네이비 계열 ========== */
  --color-navy: #1B2A4E;        /* 메인 네이비 (로고, 제목) */
  --color-navy-dark: #0F1A2E;   /* 진한 네이비 (Footer 배경) */
  --color-navy-light: #2C3E5C;  /* 밝은 네이비 */

  /* ========== ACCENT - 골드 계열 ========== */
  --color-gold: #C9A962;        /* 메인 골드 (버튼, 강조, 아이콘) */
  --color-gold-light: #D4BC7D;  /* 밝은 골드 */
  --color-gold-dark: #A68B4B;   /* 진한 골드 (호버 상태) */

  /* ========== NEUTRAL - 그레이 계열 ========== */
  --color-white: #FFFFFF;       /* 흰색 */
  --color-ivory: #F8F7F4;       /* 아이보리 (섹션 배경) */
  --color-gray-100: #F5F5F5;    /* 매우 밝은 회색 */
  --color-gray-200: #E8E8E8;    /* 테두리 색상 */
  --color-gray-300: #D1D1D1;
  --color-gray-500: #8A8A8A;    /* 설명 텍스트 */
  --color-gray-700: #4A4A4A;    /* 본문 텍스트 */
  --color-gray-900: #1A1A1A;    /* 진한 텍스트 */

  /* ========== SEMANTIC - 의미 색상 ========== */
  --color-success: #2E7D5A;     /* 성공 (초록) */
  --color-error: #C53030;       /* 에러 (빨강) */
}
```

### 색상 변경 예시

#### 골드 → 레드 톤으로 변경
```css
--color-gold: #C53030;
--color-gold-light: #E05050;
--color-gold-dark: #A02020;
```

#### 네이비 → 다크 그린으로 변경
```css
--color-navy: #1B4E3E;
--color-navy-dark: #0F2E24;
--color-navy-light: #2C5C4A;
```

#### 골드 → 에메랄드로 변경
```css
--color-gold: #2E7D5A;
--color-gold-light: #3D9B70;
--color-gold-dark: #1F5C40;
```

---

## 폰트 변경

### CSS 변수 위치: `css/style.css` 31~34번 줄

```css
/* 제목용 (세리프 - 권위있는 느낌) */
--font-display: 'Cormorant Garamond', 'Noto Serif KR', Georgia, serif;

/* 본문용 (산세리프 - 가독성) */
--font-body: 'Pretendard', -apple-system, BlinkMacSystemFont, sans-serif;

/* 영문 강조용 */
--font-accent: 'Montserrat', sans-serif;
```

### 폰트 변경 방법

1. **HTML 파일의 `<head>`에서 Google Fonts 링크 수정** (모든 HTML 파일)

```html
<link href="https://fonts.googleapis.com/css2?family=새폰트명:wght@400;500;600&display=swap" rel="stylesheet">
```

2. **CSS 변수 수정**

```css
--font-display: '새폰트명', serif;
```

### 추천 폰트 조합

| 용도 | 현재 폰트 | 대안 1 | 대안 2 |
|------|----------|--------|--------|
| 제목 | Cormorant Garamond | Playfair Display | Noto Serif KR |
| 본문 | Pretendard | Noto Sans KR | Spoqa Han Sans Neo |
| 영문 | Montserrat | Inter | Poppins |

---

## 간격/여백 조정

### CSS 변수 위치: `css/style.css` 36~44번 줄

```css
--space-xs: 0.5rem;    /* 8px - 아주 작은 간격 */
--space-sm: 1rem;      /* 16px - 작은 간격 */
--space-md: 1.5rem;    /* 24px - 중간 간격 */
--space-lg: 2rem;      /* 32px - 큰 간격 */
--space-xl: 3rem;      /* 48px - 아주 큰 간격 */
--space-2xl: 4rem;     /* 64px */
--space-3xl: 6rem;     /* 96px */
--space-4xl: 8rem;     /* 128px - 섹션 간격 */
```

### 전체적으로 여백 늘리기
```css
--space-sm: 1.25rem;   /* 16px → 20px */
--space-md: 2rem;      /* 24px → 32px */
--space-lg: 2.5rem;    /* 32px → 40px */
```

---

## 컴포넌트별 수정 위치

| 컴포넌트 | CSS 줄 번호 | 설명 |
|----------|-------------|------|
| **네비게이션** | 177~323 | 상단 메뉴바, 모바일 메뉴 |
| **버튼** | 325~378 | .btn-primary, .btn-secondary 등 |
| **Hero 섹션** | 379~465 | 메인 페이지 상단 영역 |
| **Trust 지표** | 466~502 | 연혁, 승소율 등 숫자 표시 |
| **Practice 카드** | 503~584 | 업무 분야 카드 |
| **Why 섹션** | 585~628 | 선택 이유 그리드 |
| **CTA 섹션** | 629~666 | Call-to-Action 배너 |
| **Page Header** | 667~701 | 서브페이지 상단 헤더 |
| **About 페이지** | 702~821 | 타임라인, 가치 카드 |
| **Team 페이지** | 822~889 | 변호사 카드 |
| **Cases 페이지** | 890~973 | 필터, 사례 카드 |
| **Contact 페이지** | 974~1066 | 폼, 연락처 정보 |
| **Footer** | 1067~1167 | 하단 영역 |
| **유틸리티** | 1168~1191 | 애니메이션, 헬퍼 클래스 |

---

## 반응형 디자인

### 브레이크포인트

```css
/* 모바일 (기본) */
/* 모든 스타일이 모바일 우선으로 작성됨 */

/* 태블릿 */
@media (min-width: 768px) { ... }

/* 데스크톱 */
@media (min-width: 1024px) { ... }

/* 와이드 스크린 */
@media (min-width: 1280px) { ... }
```

### 반응형 수정 예시

모바일에서 네비게이션 메뉴 배경색 변경:
```css
@media (max-width: 767px) {
  .nav-menu {
    background: var(--color-navy);  /* 흰색 → 네이비 */
  }
  .nav-link {
    color: var(--color-white);
  }
}
```

---

## 애니메이션

### 트랜지션 속도: `css/style.css` 46~49번 줄

```css
--transition-fast: 150ms ease;    /* 빠른 (호버) */
--transition-normal: 300ms ease;  /* 일반 */
--transition-slow: 500ms ease;    /* 느린 (페이드인) */
```

### 페이드인 애니메이션: 1169~1178번 줄

```css
.fade-in {
  opacity: 0;
  transform: translateY(20px);    /* 아래에서 위로 등장 */
  transition: opacity var(--transition-slow),
              transform var(--transition-slow);
}

.fade-in.visible {
  opacity: 1;
  transform: translateY(0);
}
```

### 애니메이션 끄기

모든 애니메이션 비활성화:
```css
.fade-in {
  opacity: 1;
  transform: none;
}
```

---

## 아이콘 수정

모든 아이콘은 **인라인 SVG**로 구현되어 있습니다.

### 아이콘 색상 변경

SVG에 `stroke="currentColor"`가 적용되어 있어 부모 요소의 `color` 속성을 상속받습니다.

```css
/* 네비게이션 로고 아이콘 색상 */
.nav-logo svg {
  color: var(--color-gold);  /* 다른 색으로 변경 가능 */
}
```

### 아이콘 크기 변경

```css
.practice-icon {
  width: 48px;   /* 기본 48px */
  height: 48px;
}
```

### 새 아이콘 추가하기

[Feather Icons](https://feathericons.com/) 또는 [Heroicons](https://heroicons.com/)에서 SVG 코드를 복사하여 사용:

```html
<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5">
  <!-- 아이콘 path -->
</svg>
```

---

## 실전 예제

### 예제 1: 브랜드 색상 전체 변경 (골드 → 터콰이즈)

`css/style.css` 수정:

```css
/* 변경 전 */
--color-gold: #C9A962;
--color-gold-light: #D4BC7D;
--color-gold-dark: #A68B4B;

/* 변경 후 */
--color-gold: #20B2AA;
--color-gold-light: #48D1CC;
--color-gold-dark: #008B8B;
```

이 한 곳만 수정하면 버튼, 아이콘, 강조 텍스트 등 모든 골드 색상이 터콰이즈로 변경됩니다.

### 예제 2: 버튼 모서리 둥글게

```css
/* css/style.css 337번 줄 */
.btn {
  border-radius: 2px;   /* 현재 값 */
  /* border-radius: 25px; */  /* 둥근 버튼으로 변경 */
}
```

### 예제 3: Hero 섹션 배경 이미지 추가

```css
/* css/style.css 396~399번 줄 */
.hero::before {
  background: url('../assets/images/hero-bg.jpg') center/cover no-repeat;
  opacity: 0.15;  /* 투명도 조절 (0.3으로 높이면 더 선명) */
}
```

1. `assets/images/` 폴더에 `hero-bg.jpg` 이미지 추가
2. `opacity` 값을 조절하여 이미지 선명도 조정

### 예제 4: 카드 그림자 강하게

```css
/* css/style.css 52~54번 줄 */
--shadow-sm: 0 2px 8px rgba(27, 42, 78, 0.06);
--shadow-md: 0 4px 16px rgba(27, 42, 78, 0.08);
--shadow-lg: 0 8px 32px rgba(27, 42, 78, 0.12);

/* 더 강한 그림자로 변경 */
--shadow-sm: 0 4px 12px rgba(27, 42, 78, 0.10);
--shadow-md: 0 8px 24px rgba(27, 42, 78, 0.15);
--shadow-lg: 0 16px 48px rgba(27, 42, 78, 0.20);
```

---

## 빠른 참조 표

| 변경 항목 | 수정 파일 | 줄 번호 |
|----------|----------|---------|
| 메인 색상 (골드) | style.css | 13~15 |
| 보조 색상 (네이비) | style.css | 8~10 |
| 배경 색상 | style.css | 18~19 |
| 제목 폰트 | style.css | 32 |
| 본문 폰트 | style.css | 33 |
| 섹션 간격 | style.css | 36~44 |
| 버튼 스타일 | style.css | 325~378 |
| 애니메이션 속도 | style.css | 46~49 |
| 그림자 강도 | style.css | 52~54 |

---

## 로컬 테스트 방법

```bash
cd /Users/miaro/claude/coffee/lawyer
python -m http.server 8000
```

브라우저에서 http://localhost:8000 접속하여 변경사항을 확인하세요.

---

*이 문서는 RIGHTWAY 법률사무소 홈페이지 디자인 관리를 위해 작성되었습니다.*
