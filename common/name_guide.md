# 📝 네이밍 규칙 가이드 (React 프로젝트 기준)

## ✨ 목적
- 코드의 **일관성** 유지
- 협업자 간 **명확한 커뮤니케이션**
- 검색/리팩토링/리뷰의 **생산성 향상**
- **폴더, 컴포넌트, 변수, 함수, 파일명** 등에서 혼동 방지

---

## 1. 📁 폴더 & 파일명

| 항목 | 규칙 | 예시 |
|------|------|------|
| 폴더명 | `kebab-case` | `user-profile`, `product-detail` |
| 컴포넌트 파일 | `PascalCase.tsx` | `UserCard.tsx`, `Header.tsx` |
| 일반 유틸 파일 | `camelCase.ts` | `formatDate.ts`, `validateEmail.ts` |
| 훅 파일 | `use + PascalCase.ts` 또는 `use + camelCase.ts` | `useModal.ts`, `useDebounce.ts` |
| 스타일 파일 | `컴포넌트명.module.css` 또는 `.scss` | `Button.module.css` |

---

## 2. 🧱 컴포넌트

- **컴포넌트명은 항상 PascalCase**
- 파일명과 컴포넌트명은 반드시 동일하게 작성

```tsx
// ❌ bad
function buttonComponent() { ... }

// ✅ good
function ButtonComponent() { ... }

export default ButtonComponent;
```

## 3. 🔠 변수/상수명

| 종류          | 규칙                | 예시                        |
|---------------|---------------------|-----------------------------|
| 일반 변수     | `camelCase`         | `userName`, `isLoggedIn`    |
| boolean 변수  | `is/has/should` 접두 | `isActive`, `hasPermission` |
| 상수          | `UPPER_SNAKE_CASE`  | `API_BASE_URL`, `MAX_ITEMS` |

```ts
// ✅ good
const userName = "노미";
const IS_PRODUCTION = process.env.NODE_ENV === 'production';
```
## 4. 🔁 함수 및 이벤트 핸들러

| 종류          | 규칙                           | 예시                             |
|---------------|--------------------------------|----------------------------------|
| 일반 함수     | `camelCase`                    | `fetchUserData`, `handleLogin`  |
| 이벤트 핸들러 | `handle` + 동작 대상           | `handleClick`, `handleInputChange` |
| 콜백/리스너   | `on` + 동작 대상               | `onSubmit`, `onClose`           |

```tsx
// ✅ good
const handleInputChange = (e: React.ChangeEvent<HTMLInputElement>) => {
  setValue(e.target.value);
};
```
## 5. 🪝 커스텀 Hook

- 항상 `use`로 시작합니다.
- 기능이 명확하게 드러나도록 이름을 작성합니다.
- 파일명도 동일하게 `useSomething.ts` 형식으로 작성합니다.

### ✅ 예시

```ts
// 사용 예시
useModal()
useAuth()
useDebounce()
useOutsideClick()
```
## 6. 🎨 스타일링

### ✅ CSS Modules 사용 시

- 파일명은 `컴포넌트명.module.css` 또는 `.scss`로 작성합니다.
- 클래스명은 `camelCase`로 작성합니다.

```css
/* Button.module.css */
.primaryButton {
  background-color: blue;
  color: white;
}
```

### ✅ Tailwind CSS 사용 시
- 클래스명을 HTML 요소에 직접 작성합니다.
- 순서는 레이아웃 → 박스 → 텍스트 → 색상 순으로 그룹핑을 권장합니다.
- 반복되는 스타일은 clsx, tailwind-variants, @apply 등을 활용해 관리합니다.
```tsx
// 기본 사용 예시
<button className="w-full px-4 py-2 bg-blue-500 text-white rounded-lg shadow">
  확인
</button>

// 반복 스타일 관리 예시 (clsx 사용 시)
const buttonClass = clsx(
  'px-4 py-2 rounded-lg',
  isActive ? 'bg-blue-500 text-white' : 'bg-gray-100 text-gray-700'
);
```
