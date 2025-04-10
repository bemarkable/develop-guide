📘 외부 협업 개발 가이드 (HTML, CSS, JS, React)
# 📘 외부 협업 개발 가이드 (HTML, CSS, JS, React)

---

## 1. 📌 프로젝트 개요
- **프로젝트명**: [여기에 입력]
- **기술 범위**: HTML / CSS / JavaScript / React
- **협업 대상**: 외부 프론트엔드 개발사
- **목표**: 일관된 UI/UX와 유지보수 가능한 코드 기반 협업

---

## 2. 💻 기술 스택
- **React**: 18 이상
- **JavaScript**: ES6+ 사용
- **CSS**: 기본 CSS 또는 SCSS (단, 모듈화 권장)
- **상태 관리**: useState / useEffect (간단한 수준)
- **패키지 매니저**: npm or yarn
- **번들러/환경**: Vite or CRA

---

## 3. 🗂 디렉토리 구조 및 네이밍
```
src/
├── components/   # 재사용 가능한 컴포넌트
├── pages/        # 페이지 단위 컴포넌트
├── styles/       # 전역 스타일, CSS Modules
├── assets/       # 이미지, 아이콘 등
├── hooks/        # 커스텀 훅
└── utils/        # 공통 함수
```
- **컴포넌트 명**: `PascalCase` (예: `UserCard.js`)
- **파일 명**: `camelCase.js`, 스타일은 `module.css` 혹은 `scss`
- **클래스 명**: BEM 방식 권장 (`.user-card__title`)

---

## 4. 🎨 스타일 가이드
- **CSS 설계**: 가능한 경우 CSS Module 사용 (`.module.css`)
- **단위**: rem / % / vw 사용 권장
- **반응형**: 모바일 우선 (min-width 미디어쿼리)
- **공통 색상/폰트**:

```css
:root {
  --primary-color: #3366ff;
  --font-main: 'Noto Sans KR', sans-serif;
}
```
---
## 5. ⚛ React 컴포넌트 작성 규칙
- **함수형 컴포넌트 사용**
- **필요한 경우에만 state 관리**
- **컴포넌트는 1가지 역할만 수행**
- **props는 명확하게 정의하고, 불필요한 전달 지양**
- **불변성 유지 (spread, map, filter 등 활용)**
```
jsx
function UserCard({ name }) {
  return <div className="user-card">{name}</div>;
}
```

---
## 6. ✅ 코드 컨벤션
- **ESLint & Prettier 설정 제공 예정**
- **세미콜론 사용: 항상 사용**
- **인덴트: 2 spaces**
- **문자열: 작은따옴표 '' 사용**
- **주석: 꼭 필요한 경우만 작성하며, 명확하게 기술**
---
## 7. 🔁 Git 규칙
- **브랜치 네이밍: feature/, fix/, hotfix/**
- **커밋 메시지 포맷:**
```
[Feat] 유저 카드 컴포넌트 생성
[Fix] 버튼 hover 이슈 수정
[Refactor] 로직 정리
```
---
## 8. 📤 PR 규칙
- **PR은 단일 기능 단위로 작게**
- **리뷰어 지정 필수**
- **제목 & 설명은 명확하게 작성**
- **리뷰 후 merge는 팀장/담당자 확인 후 수행**
---
## 9. 📄 문서 & 자료 위치
- **디자인 시안**: [Figma 링크]
- **API 명세**: [Swagger / Notion 링크]
- **컴포넌트 레퍼런스**: [Storybook or 캡처 정리 URL]
- **Notion 링크**: [프로젝트 대시보드]
---
## 10. 📞 커뮤니케이션
- **Slack 채널**: #project-frontend
- **정기 회의**: 매주 수요일 오후 3시 (Google Meet)
- **이슈 공유 방법**: Slack 또는 Notion에 티켓 작성
---
담당자:
기술: 이름 (이메일)
PM: 이름 (이메일)

