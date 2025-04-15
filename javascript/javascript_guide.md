
# 📘 JavaScript 프로젝트 코드 가이드

## 🧭 목적 및 대상

본 문서는 JavaScript 기반의 프론트엔드 프로젝트에서 코드의 일관성과 협업 효율성을 높이기 위한 가이드입니다.

- **목적**
  - 코드 스타일 통일
  - 유지보수성과 가독성 향상
  - 신규 개발자 온보딩 지원

- **대상**
  - JavaScript를 사용하는 모든 프론트엔드/웹 개발자
  - React 기반 프로젝트 포함

---

## 1. ✨ 기본 코드 스타일

| 항목         | 규칙                        |
|--------------|-----------------------------|
| 들여쓰기      | 2 spaces                    |
| 세미콜론      | 항상 사용 (`;`)             |
| 따옴표        | 싱글 쿼트 (`'`)             |
| 줄 끝 쉼표    | 마지막 요소 뒤에도 쉼표 포함 |
| 괄호 위치     | K&R 스타일 권장             |

> 💡 대부분 Prettier 및 ESLint로 자동 포맷팅 설정

---

## 2. 📦 변수 선언 규칙

- `const`를 기본으로 사용하고, 변경이 필요한 경우에만 `let`을 사용합니다.
- `var`는 절대 사용하지 않습니다.
- 변수명은 `camelCase`를 사용합니다.
- Boolean 변수는 `is`, `has`, `should` 등의 접두사를 사용합니다.

### ✅ 예시
```
js
const userName = '노미';
let isActive = true;
```

---

## 🧩 함수 작성 규칙

- 화살표 함수를 기본으로 사용합니다.
- 함수명은 동사로 시작합니다. (get, fetch, render, handle 등)
- 한 함수에 하나의 역할만 부여합니다 (단일 책임 원칙).

### ✅ 예시
```
const handleLogin = (id, pw) => {
  return loginApi(id, pw);
};
```

---

## 🔁 조건문 & 반복문
- if는 간결하게 작성하며, 불필요한 비교 연산은 지양합니다.
- 삼항 연산자는 단순한 경우에만 사용합니다.
- map, filter, forEach 등의 고차함수 사용을 우선합니다.

### ✅ 예시
```
// ❌ bad
if (isLoggedIn === true) {}

// ✅ good
if (isLoggedIn) {}
```

---

## 🗂 파일 및 모듈 구조
- 기능 단위로 파일을 분리합니다.
- 하나의 파일은 하나의 역할을 가집니다.
- 파일명은 camelCase.js 또는 kebab-case.js로 작성합니다.

### ✅ 예시
```
src/
├── components/
├── pages/
├── utils/
├── constants/
└── services/
```

---

## 6. 📥 import 정리 기준

### ✅ import 순서

1. **외부 라이브러리** (예: react, axios 등)
2. **내부 라이브러리/유틸** (예: utils, constants, hooks 등)
3. **상대 경로 컴포넌트/스타일** (예: `./components`, `../styles` 등)

각 블록은 **한 줄 띄어쓰기**로 구분합니다.

### ✅ 예시

```js
// 외부 라이브러리
import React from 'react';
import axios from 'axios';

// 내부 경로 import
import { formatDate } from '@/utils/date';
import { API_USER_LIST } from '@/constants/api';

// 상대 경로 import
import Button from './Button';
import styles from './Main.module.css';
```

---

## 🧪 테스트 코드 작성 규칙
- 테스트 파일명은 컴포넌트명.test.js
- 테스트는 단위 테스트 우선
- describe, it, expect 등 BDD 스타일 사용 권장

### ✅ 예시

```
describe('LoginForm', () => {
  it('should render input fields', () => {
    render(<LoginForm />);
    expect(screen.getByPlaceholderText('ID')).toBeInTheDocument();
  });
});
```

## ⚙️ ESLint & Prettier 설정
- 코드 포맷 통일을 위해 ESLint + Prettier 설정을 프로젝트에 포함합니다.
- 프로젝트 루트에 .eslintrc.js, .prettierrc 파일 작성

### ✅ ESLint 설정 예시 (.eslintrc.js)
```
module.exports = {
  extends: ['eslint:recommended', 'plugin:react/recommended'],
  env: {
    browser: true,
    es2021: true,
  },
  rules: {
    semi: ['error', 'always'],
    quotes: ['error', 'single'],
    'react/prop-types': 'off',
  },
};
```

### ✅ Prettier 설정 예시 (.prettierrc)
```
{
  "semi": true,
  "singleQuote": true,
  "tabWidth": 2,
  "trailingComma": "all"
}

```

## 9. 🧠 네이밍 규칙 요약표

| 항목              | 네이밍 규칙           | 예시                        |
|-------------------|------------------------|-----------------------------|
| 변수, 함수        | `camelCase`            | `getUser`, `isLoading`      |
| 상수              | `UPPER_SNAKE_CASE`     | `API_BASE_URL`, `MAX_COUNT` |
| 컴포넌트 이름     | `PascalCase`           | `UserCard`, `MainLayout`    |
| 파일/폴더 이름    | `kebab-case` 또는 `camelCase` | `user-service.js`, `useAuth.js` |

---

## 10. 🚫 금지 사항 및 주의사항

### ❌ 금지 항목
- `var` 키워드 사용 금지 → 항상 `const` 또는 `let` 사용
- `any` 타입 사용 지양 (TypeScript 사용 시)
- `console.log` 사용 금지  
  → 디버깅 시 `console.debug` 또는 로그 유틸 사용
- 의미 없는 주석 작성 금지

### ✅ 주석 작성 가이드

```
js
// ❌ 의미 없는 주석
// 로그인 처리
const login = () => {};

// ✅ 의미 있는 주석
/**
 * 사용자 로그인 요청을 전송하고,
 * 응답 받은 토큰을 localStorage에 저장합니다.
 */
const login = () => {
  const token = await requestLogin();
  localStorage.setItem('token', token);
};
const login = () => { ... };
``