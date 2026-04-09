# 휴먼텍 차세대 웹 시스템 (Showcase Project)

## 1. 프로젝트 전략 및 목표

- **대상:** (주)휴먼텍 (Panasonic 전자 소재 기술 영업 및 유통 전문 기업)
- **목표:** DX 역량 증명을 통한 대표이사 면접 시연용 쇼케이스 (2026. 04. 17 완성)
- **핵심 가치:** - Vercel 스타일의 극강의 미니멀리즘 구현
    - 압도적 성능 및 실무 중심의 Client Portal 구축
    - 다국어 대응을 통한 글로벌 비즈니스 역량 강조

## 2. 기술 스택 및 환경 (Tech Stack)

- **Runtime:** Node.js v22.12.0 (Vercel 배포 버전과 일치)
- **Package Manager:** pnpm
- **Framework:** Astro v5.18.1 (Pure JavaScript 모드 - 빌드 안정성 우선)
- **Styling:** Tailwind CSS v4.2.2 (@tailwindcss/vite 기반)
- **Backend:** Supabase (Auth, DB, Storage)
- **IDE:** Cursor (Claude 3.5 Sonnet 고정)
- **Deployment:** Vercel (GitHub 연동 및 자동 배포)

## 3. 핵심 사양 및 디자인 시스템

### 3.1 디자인 원칙 (Vercel-Inspired Minimal)

- **Concept:** 'Geist' 디자인 언어 기반의 정밀한 화이트 레이아웃
- **Layout:** #FFFFFF 중심의 공간감, 1px 테두리(#EAEAEA)를 활용한 구획 분리
- **Typography:** Inter/Geist 산세리프 폰트, 가독성 중심의 행간 확보
- **Interaction:** 절제된 마이크로 인터렉션 및 스크롤 시 Glassmorphism 효과

### 3.2 핵심 기능

- **반응형(Responsive):** Mobile / Tablet / Desktop 전체 대응
- **다국어(i18n):** URL 경로 기반 분리 (`/ko`, `/ja`, `/en`) 및 실시간 스위처 제공
- **Client Portal:** 로그인 기반의 기술 자료실 및 고객 지원 기능

## 4. 사이트 구조 (Information Architecture)

- **Home:** 파트너십 강조 및 핵심 제품 3종 벤토 그리드(Bento Grid) 배치
- **About:** 회사 개요, CEO 인사말, 연혁, 오시는 길 (통합 롱페이지)
- **Products:** PCB 재료 / 부자재 / Machine (필터링 및 상세 보기)
- **Support:** Client Portal (로그인), 통합 문의 폼

## 5. 디렉토리 구조 규칙

```text
/src
 ├── assets/        # 이미지, 아이콘, 로고 (SVG 권장)
 ├── components/    # 재사용 UI 컴포넌트 (PascalCase)
 ├── layouts/       # 페이지 공통 레이아웃 (Vercel 스타일)
 ├── pages/         # 파일 기반 라우팅 (언어별 폴더 구조: ko/, ja/, en/)
 ├── styles/        # global.css 및 Tailwind 4 설정
 ├── lib/           # Supabase 클라이언트 및 유틸리티 함수
 └── content/       # 제품 데이터 및 뉴스용 마크다운/JSON
```
