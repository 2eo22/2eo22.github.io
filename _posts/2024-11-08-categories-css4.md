---
title: "[CSS] 선택자(Selector)"
excerpt: "CSS 선택자에 대해 알아보자 "

categories:
  - css
tags:
  - [css]

permalink: /categories/css/4

toc: true
toc_sticky: true

date: 2024-11-08
last_modified_at: 2024-11-08
---

## 🦥 본문
# CSS 선택자(Selector)

CSS에서 가장 중요한 개념인 선택자에 대해 알아보겠습니다.

## 기본 선택자

| 선택자 종류     | 문법              | 설명                                                                                     |
| --------------- | ----------------- | ---------------------------------------------------------------------------------------- |
| 전체 선택자     | `* {속성 : 값; }` | 모든 요소를 선택 / 중괄호 앞에 `*`을 붙임                                                |
| 태그 선택자     | `태그명 {속성 : 값;}` | 주어진 요소 이름으로 원하는 요소를 선택                                                   |
| 아이디 선택자   | `#아이디명 {속성 : 값;}` | - 지정한 `id` 값을 이용하여 요소를 선택 <br> - 중괄호 앞에 `#`을 붙임 <br> * `id`는 JAVA와 연결하여 많이 쓰인다 |
| 클래스 선택자   | `.클래스명 {속성 : 값;}` | - 지정한 `class` 값을 이용하여 요소를 선택 <br> - 중괄호 앞에 `.`을 붙임 <br> - `class`는 CSS와 많이 쓰이는 선택자입니다. |
| 그룹 선택자     | `A, B, C {속성 : 값;}` | 여러 태그에 동일한 스타일 지정을 원할 경우 태그를 콤마로 구분                              |

> ❗️ 아이디, 클래스 선택자 적용 시 태그 사이의 공백을 주의해야 합니다. 예를 들어 `A B` 사이에 공백이 없을 경우 `AB`라는 별도의 태그로 인식될 수 있습니다. 정확한 선택을 통해 정확한 위치에 스타일을 적용하는 것이 중요합니다.

## DESC 선택자 (형제 선택자)

| 선택자 이름       | 문법              | 설명                                                                                     |
| ----------------- | ----------------- | ---------------------------------------------------------------------------------------- |
| 자손 선택자       | `A B {속성: 값;}` | - 태그 사이에 공백으로 표현 <br> - `Tag(조상) Tag(자손) {...}` <br> - `A` 태그를 조상, `B` 태그를 자손으로 인식하여 하위 요소로 취급합니다. |
| 자식 선택자       | `A > B {속성: 값;}` | - 태그 사이에 `>`로 표현 <br> - `Tag(부모) > Tag(자식) {...}` <br> - `A` 태그를 부모, `B` 태그를 자식으로 인식합니다. |
| 인접 형제 선택자  | `A + B {속성: 값;}` | - 태그 사이에 `+`로 표현 <br> - 앞 선택자의 형제 요소 중 바로 다음에 따라오는 요소를 선택합니다. |
| 일반 형제 선택자  | `A ~ B {속성: 값;}` | - 태그 사이에 `~`로 표현 <br> - 뒤에 따라오는 모든 형제 요소를 선택합니다.               |

## 속성 선택자 (Attribute Selector)
태그의 속성을 통해 원하는 요소를 선택할 때 사용합니다.

| 문법                  | 설명                                                               |
| --------------------- | ------------------------------------------------------------------ |
| `[속성 명] {속성: 값;}` | 해당 속성명이 있는 요소만 선택                                       |
| `[속성 명=값] {속성: 값;}` | 정확히 해당 값과 일치하는 속성 값을 가진 요소만 선택                  |
| `[속성 명^="값"] {속성: 값;}` | 해당 속성 값이 특정 문자열로 시작하는 요소만 선택                    |

## 의사 클래스 선택자 (Pseudo-Class Selector)
콜론 `:`을 사용하여 선택합니다. CSS3에서는 `::`로 표시할 수도 있지만, CSS2처럼 `:` 한 개를 사용해도 됩니다.

| 문법               | 설명                                                                 |
| ------------------ | -------------------------------------------------------------------- |
| `:hover`           | 요소에 마우스를 올렸을 때                                             |
| `:link`            | 모든 `a` 태그를 선택                                                  |
| `:visited`         | 이미 방문한 링크를 선택                                               |
| `:active`          | `a`, `input`, `button` 등을 누르는 순간 선택                          |
| `:focus`           | `[tab]` 키로 포커스가 적용된 요소 선택                               |
| `:focus-within`    | 자식 요소 중 포커스가 적용되었을 때 선택                               |

## 의사 요소 선택자 (Pseudo-Element Selector)
CSS3에서는 콜론 두 개 `::`를 사용하지만, CSS2처럼 `:`를 한 개 사용해도 됩니다.

| 문법       | 설명                                                                 |
| ---------- | -------------------------------------------------------------------- |
| `::before` | 콘텐츠 앞 공간을 선택                                                 |
| `::after`  | 콘텐츠 뒤 공간을 선택                                                 |

## 일반구조 선택자 (Pseudo Class Selector)
형제 요소 중 인덱스 번호를 이용하여 요소를 선택하며, 선택자 뒤에 `:`를 붙입니다.

| 선택자                  | 설명                                                   |
| ----------------------- | ------------------------------------------------------ |
| `:first-child`          | 첫 번째 요소를 선택                                     |
| `:last-child`           | 마지막 요소를 선택                                      |
| `:nth-child(수열)`      | 수열 번째 요소를 선택 (`nth-child(2)`는 두 번째 요소)    |
| `:nth-last-child(수열)` | 마지막에서 수열 번째 요소 선택 (`nth-last-child(2)`)     |

> `nth-child()`와 `nth-last-child()`의 `()` 안에는 수열을 입력하여 특정 목록을 지정할 수 있습니다. 예를 들어 `(2n)` 또는 `(even)`을 사용하면 짝수 요소에 스타일을 적용하고, `(2n+1)`은 홀수 요소에 스타일을 지정할 수 있습니다.

## 부정 선택자

| 선택자               | 설명                                               |
| -------------------- | -------------------------------------------------- |
| `:not(선택자)`       | 괄호 안의 태그를 제외한 모든 요소에 스타일 적용    |

```html
<style>
p:not(:last-child) {...}
</style>


## 상태 선택자

- `input`과 `button` 태그에 많이 사용된다

| 선택자            | 설명                                       |
| ----------------- | ------------------------------------------ |
| `input:disabled`  | 사용 불가 상태인 `input` 요소를 선택        |
| `input:checked`   | 체크된 `input` 요소를 선택                  |
| `:target`         | 클릭된 링크의 타겟을 받은 요소를 선택       |