# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

**RIGHTWAY (라이트웨이)** - 법률사무소 홈페이지

"올바른 길로 안내합니다" - 의뢰인의 권리를 지키고 정의를 실현하는 신뢰할 수 있는 법률 파트너.

## Site Structure

```
├── index.html          # 메인 페이지 (Hero + 핵심 서비스 소개)
├── about.html          # 서브페이지 1: 사무소 소개
├── practice.html       # 서브페이지 2: 업무 분야
├── team.html           # 서브페이지 3: 변호사 소개
├── cases.html          # 서브페이지 4: 성공 사례
├── contact.html        # 서브페이지 5: 상담 문의
├── css/
│   └── style.css
├── js/
│   └── main.js
└── assets/
    ├── icons/          # SVG 아이콘
    └── images/         # 이미지 파일
```

## Navigation Menu

| 메뉴 | 파일 | 설명 |
|------|------|------|
| HOME | index.html | 메인 랜딩 페이지 |
| ABOUT | about.html | 사무소 소개 & 연혁 |
| PRACTICE | practice.html | 업무 분야 (민사, 형사, 기업 등) |
| TEAM | team.html | 변호사 프로필 |
| CASES | cases.html | 주요 성공 사례 |
| CONTACT | contact.html | 상담 예약 & 오시는 길 |

## Brand Identity

### Brand Concept
- **키워드**: 신뢰, 전문성, 정의, 권위, 성실
- **톤앤매너**: 클래식하고 격조 있는, 전문적이면서도 따뜻한
- **무드**: 깊은 네이비 + 골드 악센트 + 깨끗한 화이트

### Color Palette

```css
:root {
  /* Primary - 신뢰와 권위의 네이비 */
  --color-navy: #1B2A4E;
  --color-navy-dark: #0F1A2E;
  --color-navy-light: #2C3E5C;

  /* Accent - 품격의 골드 */
  --color-gold: #C9A962;
  --color-gold-light: #D4BC7D;
  --color-gold-dark: #A68B4B;

  /* Neutral - 깨끗하고 명료한 */
  --color-white: #FFFFFF;
  --color-ivory: #F8F7F4;
  --color-gray-100: #F1F1F1;
  --color-gray-300: #D1D1D1;
  --color-gray-500: #8A8A8A;
  --color-gray-700: #4A4A4A;
  --color-gray-900: #1A1A1A;

  /* Semantic */
  --color-success: #2E7D5A;
  --color-error: #C53030;
}
```

### Typography

```css
/* 헤딩 - 권위 있는 세리프 */
--font-display: 'Cormorant Garamond', 'Noto Serif KR', serif;

/* 본문 - 가독성 좋은 산세리프 */
--font-body: 'Pretendard', -apple-system, BlinkMacSystemFont, sans-serif;

/* 악센트 - 정제된 영문 */
--font-accent: 'Montserrat', sans-serif;
```

### Icon Style

SVG 아이콘 사용 - 법률 사무소의 신뢰감을 전달:
- **스타일**: Outline 또는 Light fill (선 두께 1.5px)
- **크기**: 24px, 32px, 48px, 64px
- **색상**: 네이비 또는 골드, currentColor 활용

핵심 아이콘:
- 저울 (Justice Scale) - 공정함
- 기둥 (Pillar/Column) - 안정성
- 방패 (Shield) - 보호
- 법전/책 (Book/Gavel) - 전문성
- 악수 (Handshake) - 신뢰
- 건물 (Building) - 사무소
- 사람 (Person/Team) - 변호사
- 체크마크 (Checkmark) - 성공
- 전화/메일 (Phone/Email) - 연락

## Page Specifications

### 1. 메인 페이지 (index.html)

```
┌─────────────────────────────────────┐
│           NAVIGATION                │
├─────────────────────────────────────┤
│                                     │
│           HERO SECTION              │
│    "당신의 권리, 올바른 길로"         │
│      [상담 예약] [업무분야 보기]       │
│                                     │
├─────────────────────────────────────┤
│         TRUST INDICATORS            │
│   [설립연도] [승소율] [상담건수]       │
├─────────────────────────────────────┤
│         PRACTICE AREAS              │
│    주요 업무 분야 카드 (3-4개)        │
├─────────────────────────────────────┤
│         WHY RIGHTWAY                │
│    선택해야 하는 이유 (차별점)         │
├─────────────────────────────────────┤
│         CONSULTATION CTA            │
│      무료 상담 안내 배너              │
├─────────────────────────────────────┤
│           FOOTER                    │
└─────────────────────────────────────┘
```

### 2. 사무소 소개 (about.html)

- 사무소 철학 및 비전
- 연혁 (타임라인)
- 미션 & 핵심 가치
- 사무소 시설 안내

### 3. 업무 분야 (practice.html)

- 민사 소송 (손해배상, 계약분쟁)
- 형사 변호 (수사단계, 재판단계)
- 기업 자문 (계약, M&A, 노무)
- 가사 (이혼, 상속, 양육권)
- 부동산 (매매, 임대차, 재개발)
- 행정 (인허가, 행정심판)

### 4. 변호사 소개 (team.html)

- 대표 변호사 프로필
- 소속 변호사 그리드
- 학력, 경력, 주요 업무 분야
- 전문가 네트워크

### 5. 성공 사례 (cases.html)

- 분야별 대표 사례
- 사건 개요, 쟁점, 결과
- 의뢰인 후기 (익명 처리)

### 6. 상담 문의 (contact.html)

- 상담 예약 폼
- 전화/이메일/카카오톡 연락처
- 오시는 길 (지도)
- 운영 시간
- 비용 안내

## Design Guidelines

### Visual Style
- **라이트 모드 기본** (신뢰감, 전문성)
- 넉넉한 여백으로 고급스러운 느낌
- 이미지는 법률 관련 (법원, 사무실, 악수 등)
- 미세한 선과 구분선으로 정돈된 레이아웃

### UI Components

#### 버튼 스타일
```css
/* Primary - 골드 배경 */
.btn-primary {
  background: var(--color-gold);
  color: var(--color-navy-dark);
  padding: 14px 32px;
  font-weight: 600;
  letter-spacing: 0.5px;
}

/* Secondary - 네이비 테두리 */
.btn-secondary {
  border: 1px solid var(--color-navy);
  color: var(--color-navy);
  background: transparent;
}
```

#### 카드 스타일
```css
.card {
  background: var(--color-white);
  border: 1px solid var(--color-gray-200);
  box-shadow: 0 2px 8px rgba(27, 42, 78, 0.06);
  padding: 32px;
}
```

### Animation
- 부드럽고 절제된 애니메이션
- 페이드인 (스크롤 트리거)
- 호버 시 미세한 상승 효과
- 과한 움직임 지양 (신뢰감 유지)

### Responsive Breakpoints
```css
/* Mobile */   @media (max-width: 767px)
/* Tablet */   @media (min-width: 768px)
/* Desktop */  @media (min-width: 1024px)
/* Wide */     @media (min-width: 1280px)
```

## Tech Stack

- **HTML5**: 시맨틱 마크업
- **CSS3**: CSS 변수, Flexbox, Grid
- **JavaScript**: Vanilla JS (폼 검증, 인터랙션)
- **Fonts**: Google Fonts (Cormorant Garamond, Montserrat, Pretendard)
- **Icons**: 인라인 SVG

## Content Guidelines

### 톤앤보이스
- **전문적**: 법률 용어를 이해하기 쉽게 설명
- **신뢰감 있는**: 과장 없이 사실에 기반한 표현
- **따뜻한**: 의뢰인의 어려움에 공감하는 어조
- **명확한**: 절차와 비용을 투명하게 안내

### 필수 포함 문구
- 법률 상담 안내 문구
- 개인정보 처리방침 링크
- 대한변호사협회 등록 정보

## Anti-Patterns (피해야 할 것)

- 과도하게 화려한 색상이나 그라디언트
- 무거운 애니메이션
- 스톡 이미지 느낌의 과장된 포즈
- 압박감을 주는 공격적인 마케팅 문구
- AI 슬롭 스타일 (보라-파랑 그라디언트 등)

## File Naming Convention

```
css/style.css
js/main.js
assets/icons/icon-scale.svg
assets/icons/icon-shield.svg
assets/icons/icon-gavel.svg
assets/images/hero-bg.jpg
assets/images/team-lawyer-01.jpg
```

## Build Commands

정적 사이트이므로 빌드 불필요. 로컬 서버 실행:

```bash
# Python
python -m http.server 8000

# Node.js (npx 사용)
npx serve .
```

## Key Differentiators

RIGHTWAY 법률사무소의 핵심 차별점:
1. **20년+ 경력**의 전문 변호사진
2. **95% 이상 승소율** (분야별 상이)
3. **명확한 비용 안내** - 숨김 비용 없음
4. **24시간 긴급 상담** 가능
5. **원스톱 법률 서비스** - 소송부터 집행까지
