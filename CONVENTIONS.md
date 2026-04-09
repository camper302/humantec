# 개발 지침 및 엄격 규칙 (Strict Conventions)

본 프로젝트는 **Astro 5** 및 **Vercel** 환경에서 에러 없는 완벽한 쇼케이스 구현을 위해 아래 규칙을 엄격히 준수합니다. AI와 협업 시 반드시 이 문서를 최우선으로 참조하십시오.

---

## 1. 명명 규칙 (Naming Conventions)

### 1.1 파일 및 폴더

- **컴포넌트:** `src/components/` 내 위치하며 **PascalCase** 사용  
  _(예: `HeroBanner.astro`, `LanguageSwitcher.jsx`)_
- **페이지 및 폴더:** `src/pages/` 내 위치하며 **kebab-case** 사용  
  _(예: `client-portal.astro`, `product-detail/`)_
- **에셋:** 모든 이미지 및 아이콘은 **kebab-case** 권장

### 1.2 코드 내부

- **변수 및 함수:** **camelCase** 사용 _(예: `isLoggedIn`, `fetchProductData`)_
- **상수:** **UPPER_SNAKE_CASE** 사용 _(예: `API_BASE_URL`)_

---

## 2. 코드 작성 및 안정성 (Anti-Error)

### 2.1 언어 및 런타임

- **Pure JavaScript:** 빌드 시 타입 에러로 인한 중단을 방지하기 위해 **TypeScript를 사용하지 않고 순수 JS**만 사용합니다.
- **Node.js 버전:** Vercel 환경과 동일한 **v22.x**를 유지합니다. (`package.json`의 `engines` 필드 준수)

### 2.2 데이터 핸들링

- **Null Check:** 모든 데이터 접근 시 **Optional Chaining(`?.`)**을 사용하여 `undefined` 에러를 원천 차단합니다.
- **Key Naming:** JSON, Props, Object의 모든 Key 값은 **camelCase**로 통일합니다.

### 2.3 보안

- **환경 변수:** API Key, Secret, Token 등 민감 정보는 반드시 `.env` 파일을 사용하며 코드 내 하드코딩을 절대 금지합니다.

---

## 3. 구조 및 성능 (Architecture & Performance)

### 3.1 경로 관리 (Import)

- **대소문자 일치:** Import 시 파일/폴더 경로의 대소문자를 실제와 100% 일치시킵니다. (Windows/Mac에서 작동해도 Linux 배포 시 오류 발생 가능성 차단)
- **Alias 활용:** 상대 경로(`../../../`) 남용을 금지하고, 필요 시 별칭을 설정하여 구조를 개선합니다.

### 3.2 최적화 및 SEO

- **이미지 접근성:** 모든 `<img>` 태그에 의미 있는 `alt` 속성을 필수로 부여합니다.
- **메타 데이터:** 각 페이지별로 고유한 `title` 및 `meta description`을 설정합니다.
- **Cleanup:** 운영 배포 전 미사용 코드(Import, Variable)와 `console.log`, `debugger`를 전면 제거합니다.

---

## 4. AI 협업 및 주석 규칙

### 4.1 주석 가이드 (Documentation)

- **학습형 주석:** 주요 컴포넌트와 함수 상단에 기능과 작동 원리를 명시합니다.
    ```javascript
    // [기능] 다국어 경로 전환
    // [원리] 현재 URL에서 locale 정보를 추출하여 선택한 언어로 리다이렉트
    ```
