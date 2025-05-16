## ✨ 프론트엔드 사전과제: 자동완성 셀렉트 박스 with 타입 분류 및 하이라이팅

### 📌 과제 목적

![question](./348952266-3f139392-b269-4a4f-80e4-11eb82afd249.gif)

이 과제는 **실시간 검색어 자동완성 UI**를 구현함으로써, 상태 관리, 문자열 처리, DOM 렌더링 최적화 능력을 확인하기 위한 과제입니다.
데이터에는 `회사`, `인물`, `국가`, `직업` 등의 타입이 포함되어 있으며, **하이라이팅 처리와 타입별 구분 출력**이 요구됩니다.

---

### ✅ 기본 과제 (필수)

#### 🎯 목표 기능

> 사용자가 입력한 텍스트에 따라 자동완성 추천 리스트를 필터링 및 출력하며, 검색어는 **하이라이팅**, 각 항목은 **타입 분류**가 되어야 합니다.

#### 📄 기능 요구사항

1. **인풋 필드**

   - 사용자가 검색어를 입력합니다.
   - 입력값이 변경될 때마다 추천 리스트가 갱신됩니다.

2. **추천 리스트 출력**

   - `dummy` 배열에서 입력값을 포함한 `description`이 있는 항목을 필터링하여 리스트로 출력합니다.
   - 필터링은 대소문자를 구분하지 않습니다.

3. **검색어 하이라이팅**

   - 리스트 항목 내에서 입력한 텍스트와 일치하는 부분을 `<strong>` 태그로 감싸서 **굵게** 표시합니다.
   - 예: `app` 입력 시 `(AAPL) <strong>App</strong>le Inc`

4. **항목 선택**

   - 리스트에서 항목 클릭 시 해당 항목의 `key`가 인풋 필드에 입력됩니다.
   - 추천 리스트는 사라집니다.

5. **타입 태그 표시**

   - 각 항목의 `type` 값을 오른쪽에 태그 형태로 함께 출력합니다. 예:

     ```
     (AAPL) Apple Inc                [COMPANY]
     ```

#### 📦 사용 데이터

```ts
export const dummy = [
  { description: "(ORCL) Oracle Corp", key: "Oracle Corp", type: "COMPANY" },
  { description: "(AAPL) Apple Inc", key: "Apple Inc", type: "COMPANY" },
  { description: "(GOOG) Google Inc", key: "Google Inc", type: "COMPANY" },
  {
    description: "(DATA) Tableau Software",
    key: "Tableau Software",
    type: "COMPANY",
  },
  { description: "Singapore", key: "Singapore", type: "COUNTRY" },
  {
    description: "Michael Jordan (NBA)",
    key: "Michael Jordan",
    type: "PEOPLE",
  },
  { description: "Larry Page (GOOG)", key: "Larry Page", type: "PEOPLE" },
  { description: "Tim Cook (AAPL)", key: "Tim Cook", type: "PEOPLE" },
  { description: "Steve Jobs (AAPL)", key: "Steve Jobs", type: "PEOPLE" },
  { description: "Programmer", key: "Programmer", type: "JOB" },
  { description: "Analyst", key: "Analyst", type: "JOB" },
  { description: "Manager", key: "Manager", type: "JOB" },
];
```

---

### 💡 심화 과제 (선택)

#### 📌 다음 기능 중 하나 이상을 추가해보세요

| 심화 항목    | 설명                                                                                  |
| ------------ | ------------------------------------------------------------------------------------- |
| 키보드 탐색  | ↑, ↓ 키로 추천어를 이동하고 `Enter`로 선택 가능                                       |
| Debounce     | 입력값 변경 시 300ms 지연 후 필터링 적용                                              |
| 섹션 그룹화  | 항목을 `type` 기준으로 그룹화하여 헤더로 구분 (`COMPANY`, `PEOPLE`, `COUNTRY`, `JOB`) |
| async mock   | 추천 데이터를 `fetchSuggestions(keyword)`를 통해 비동기로 가져오는 형태로 리팩터링    |
| 선택 후 콜백 | 항목 선택 시 console.log에 `{ key, type }` 출력                                       |
| 없음 처리    | 필터된 결과가 없으면 `"결과가 없습니다"` 출력                                         |

---

### 🧾 제출 가이드

| 항목     | 설명                                                                                          |
| -------- | --------------------------------------------------------------------------------------------- |
| 기술스택 | React, CSS IN JS 또는 Tailwind                                                                |
| 구성     | `AutoComplete.tsx`, `SuggestionItem.tsx`, `highlightText.ts`, 등 역할 기반 컴포넌트 분리 권장 |
| 제출     | GitHub 링크 or CodeSandbox 공유, README에 실행 방법 포함 시 가산점                            |

---

### ✅ 평가 포인트

| 항목                | 체크                                     |
| ------------------- | ---------------------------------------- |
| 필터링 정확성       | description에 포함된 항목만 필터링       |
| 하이라이팅 처리     | 입력값이 정확히 `<strong>` 태그로 강조됨 |
| 키보드 및 마우스 UX | 선택 동작이 자연스러움                   |
| 코드 구조           | 적절한 컴포넌트 분리 및 상태 관리        |
| 확장성              | 타입 추가 시 유연하게 동작하는 구조      |

---
