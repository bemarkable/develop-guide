# 📁 프로젝트 디렉토리 구조 가이드

React 기반의 모던 프론트엔드 프로젝트는 **재사용성과 유지보수**를 고려해 폴더 구조를 체계적으로 설계해야 합니다.  
아래는 대표적인 디렉토리 구조와 각 디렉토리의 목적, 구성 방식에 대한 상세 설명입니다.

---

## 📌 최상위 구조

```
src/ ├── assets/ ├── components/ ├── pages/ ├── styles/ ├── hooks/ ├── utils/ ├── contexts/ └── App.tsx
```


---

## 📂 assets/  
> 이미지, 아이콘, 폰트 등 정적 자산을 보관하는 디렉토리

- `images/`: 배경 이미지, 일러스트 등
- `icons/`: SVG 또는 아이콘 세트
- `fonts/`: 웹 폰트 파일

**예시**
```
assets/ ├── images/ │ └── banner.png ├── icons/ │ └── close.svg └── fonts/ └── Pretendard.woff2
```

---

## 📂 components/  
> 공통 UI 컴포넌트를 저장하는 디렉토리 (재사용 가능성이 높은 컴포넌트들)

- **원자적 구조 적용 권장 (Atomic Design)**
  - `atoms/`: Button, Input 등 기본 단위 컴포넌트
  - `molecules/`: FormGroup, ListItem 등 단위 결합 컴포넌트
  - `organisms/`: Header, Footer 등 전체 레이아웃 구성 요소

**예시**
```
components/ ├── atoms/ │ └── Button.tsx ├── molecules/ │ └── FormField.tsx └── organisms/ └── Header.tsx
```

---

## 📂 pages/  
> 라우팅 경로별 페이지 컴포넌트 정의

- 파일 기반 라우팅 구조 (`/home`, `/about`, `/product/:id` 등)
- 각 폴더 내에 `index.tsx` 사용 권장
- 페이지 내에서만 사용되는 로컬 컴포넌트는 `__components/`로 별도 관리

**예시**
```
pages/ ├── Home/ │ ├── index.tsx │ └── __components/ │ └── HomeBanner.tsx ├── Product/ │ └── index.tsx └── About/ └── index.tsx
```


---

## 📂 styles/  
> 전역 스타일, 테마 설정, Tailwind 설정 등을 포함

- `global.css`: 전역 스타일
- `reset.css`: 기본 브라우저 스타일 리셋
- `theme.ts`: 색상, 폰트 사이즈 등 전역 변수

**예시**
```
styles/ ├── global.css ├── reset.css └── theme.ts
```

---

## 📂 hooks/  
> 재사용 가능한 커스텀 훅(Custom Hooks)을 정의

- `useInput.ts`: 입력 값 관리 훅
- `useModal.ts`: 모달 상태 관리 훅
- `useFetch.ts`: API 요청 훅

**예시**
```
hooks/ ├── useInput.ts ├── useModal.ts └── useDebounce.ts
```

---

## 📂 utils/  
> 공통으로 사용하는 함수, 상수, 헬퍼 함수 등 정의

- `formatDate.ts`: 날짜 포맷 변환
- `validate.ts`: 폼 유효성 검사
- `constants.ts`: 상수 목록

**예시**

```
utils/ ├── formatDate.ts ├── validate.ts └── constants.ts
```

---

## 📂 contexts/  
> 전역 상태 관리용 React Context 파일 모음

- 전역 사용자 정보, 토스트, 다크모드 등의 상태
- `Provider`, `Context`, `useContext` Hook으로 구성

**예시**
```
contexts/ ├── AuthContext.tsx └── ThemeContext.tsx
```

---

## 🧩 기타 파일

| 파일명      | 설명 |
|-------------|------|
| `App.tsx`   | 루트 컴포넌트, 라우팅 및 전역 설정 |
| `main.tsx`  | React 앱 진입점 |
| `index.html`| Vite 또는 CRA 기본 HTML 템플릿 |
| `vite.config.ts` | 빌드 설정 파일 (Vite 사용 시) |
| `tsconfig.json`  | TypeScript 설정 파일 |

---

## 🛠️ 보조 규칙 (Best Practices)

- ✅ 각 컴포넌트는 `컴포넌트명.tsx` + `컴포넌트명.module.css` 조합 사용 (CSS Module 기준)
- ✅ 테스트 파일은 동일한 폴더에 `컴포넌트명.test.tsx`로 작성
- ✅ import 경로는 절대 경로 (`@components`, `@hooks` 등) 사용 권장
- ✅ 각 폴더에 `README.md`를 작성하여 하위 파일 목적 설명 (선택사항)

---

> 📌 프로젝트 초기에 폴더 구조와 네이밍 컨벤션을 정하고, 모든 팀원이 일관되게 사용하는 것이 중요합니다.
    협업 효율성을 위해 위 가이드를 기준으로 구성 및 유지해주세요.
