
# 📘 HTML 개발 가이드 목차

## 1. 📌 가이드 목적 및 적용 대상
- 문서의 목적
- 어떤 프로젝트/팀에 적용하는지

---

## 2. 🧱 HTML 기본 원칙
- 문법 준수 (W3C Validator 기준)
- 들여쓰기, 공백 규칙
- 속성 순서 및 정렬 기준

---

## 3. 🧠 시맨틱 마크업 (Semantic HTML)
- 시맨틱 태그의 중요성
- 주요 시맨틱 태그 설명:
  - `<header>`, `<main>`, `<section>`, `<article>`, `<aside>`, `<footer>` 등
- 시맨틱 구조 설계 예시

---

## 4. 📏 코드 작성 규칙
- 들여쓰기 방식 (2 space 또는 4 space)
- 속성 순서: `id → class → name → src/href → 기타`
- 태그는 반드시 닫기
- 태그, 속성, 값은 **소문자 사용**

---

## 5. 🔤 클래스/ID 네이밍 규칙
- 네이밍 형식: `kebab-case` 권장
- 선택: BEM(Block Element Modifier) 네이밍 원칙

---

## 6. 🌐 웹 접근성(WA) 원칙
- `alt` 속성 필수
- `label`과 `input` 연결
- 제목 태그(`<h1>` ~ `<h6>`)의 계층 구조
- `aria-*` 속성 활용

---

## 7. 📄 문서 구조 작성 가이드
- 기본 문서 템플릿 구조:
  - `<html>`, `<head>`, `<body>`
- 필수 메타태그:
  - `charset`, `viewport`, `description`, `robots` 등

---

## 8. 🔗 링크와 이미지 처리
- 경로 기준: 상대 경로 vs 절대 경로
- 외부 링크 처리 시:
  - `target="_blank"`와 `rel="noopener noreferrer"` 병행
- 이미지 태그는 반드시 `alt` 속성 포함

---

## 9. 🧪 폼(Form) 작성 가이드
- `label`과 `input`은 `for`/`id`로 연결
- 필수 입력값 시각적 표시
- `fieldset`, `legend` 활용 권장

---

## 10. 🎨 스타일과의 분리 원칙
- 인라인 스타일 사용 금지
- CSS는 외부 파일로 분리
- `<style>` 태그는 `<head>` 내에서만 사용

---

## 11. ⚠️ 자주 하는 실수 모음
- `<div>` 남용
- `<h1>` 태그 중복 사용
- 레이아웃에 `<table>` 사용
- 줄바꿈을 `<br>` 태그로 처리

---

## 12. 🛠 HTML 검사 및 테스트 도구
- [W3C Markup Validation Service](https://validator.w3.org/)
- [Google Lighthouse](https://developer.chrome.com/docs/lighthouse/overview/)
- [axe DevTools](https://www.deque.com/axe/devtools/)

---

## 13. 📚 참고 자료
- [MDN Web Docs - HTML](https://developer.mozilla.org/ko/docs/Web/HTML)
- [WHATWG - HTML Living Standard](https://html.spec.whatwg.org/multipage/)
- [국립웹접근성 연구소](https://www.wah.or.kr/)

---
