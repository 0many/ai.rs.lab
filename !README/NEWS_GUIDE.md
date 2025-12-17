# 📰 News 추가/수정 가이드

## 📌 개요
`news.html` 페이지는 연구실의 소식과 공지사항을 관리합니다.
이 가이드를 따라 새로운 뉴스를 쉽게 추가하실 수 있습니다.

---

## 📝 News 추가하기

### 1단계: news.html 파일 열기
`news.html` 파일을 에디터로 엽니다.

### 2단계: 뉴스 항목 추가 위치 찾기
`<tbody class="divide-y divide-gray-200 dark:divide-gray-700">` 섹션을 찾습니다.
**새로운 뉴스는 맨 위에 추가**합니다 (최신 순서).

### 3단계: 뉴스 항목 템플릿 복사

다음 템플릿을 복사해서 정보를 채워넣으세요:

```html
<tr class="news-item hover:bg-gray-50 dark:hover:bg-gray-800/30 transition-colors">
  <td class="px-6 py-4 text-base text-gray-600 dark:text-gray-400 text-center">번호</td>
  <td class="px-6 py-4 text-base text-gray-900 dark:text-white">뉴스 제목</td>
  <td class="px-6 py-4 text-base text-center"></td>
  <td class="px-6 py-4 text-base text-gray-600 dark:text-gray-400 text-center">날짜</td>
</tr>
```

### 4단계: 정보 입력하기

#### 기본 뉴스 (링크 없음)

```html
<tr class="news-item hover:bg-gray-50 dark:hover:bg-gray-800/30 transition-colors">
  <td class="px-6 py-4 text-base text-gray-600 dark:text-gray-400 text-center">34</td>
  <td class="px-6 py-4 text-base text-gray-900 dark:text-white">2025 한국장학재단 이공계 박사우수장학금 선정 (홍길동 연구원)</td>
  <td class="px-6 py-4 text-base text-center"></td>
  <td class="px-6 py-4 text-base text-gray-600 dark:text-gray-400 text-center">2025-12-25</td>
</tr>
```

#### 링크가 있는 뉴스

```html
<tr class="news-item hover:bg-gray-50 dark:hover:bg-gray-800/30 transition-colors">
  <td class="px-6 py-4 text-base text-gray-600 dark:text-gray-400 text-center">34</td>
  <td class="px-6 py-4 text-base text-gray-900 dark:text-white">논문 게재: Deep Learning for Remote Sensing</td>
  <td class="px-6 py-4 text-base text-center">
    <a href="https://doi.org/10.3390/rs13010001" target="_blank" class="inline-flex items-center gap-1 text-accent hover:text-blue-700 transition-colors">
      <span class="material-symbols-outlined text-base">link</span>
      Link
    </a>
  </td>
  <td class="px-6 py-4 text-base text-gray-600 dark:text-gray-400 text-center">2025-12-25</td>
</tr>
```

---

## 📋 각 필드 설명

| 필드 | 설명 | 예시 |
|------|------|------|
| **번호** | 뉴스 일련번호 (최신순으로 증가) | 34 |
| **제목** | 뉴스 제목 (한글/영문) | "2025 한국장학재단 장학금 선정" |
| **링크** | 관련 링크 (선택 사항) | https://example.com |
| **날짜** | YYYY-MM-DD 형식 | 2025-12-25 |

---

## 📋 예시

### 예시 1: 장학금 선정 소식

```html
<tr class="news-item hover:bg-gray-50 dark:hover:bg-gray-800/30 transition-colors">
  <td class="px-6 py-4 text-base text-gray-600 dark:text-gray-400 text-center">35</td>
  <td class="px-6 py-4 text-base text-gray-900 dark:text-white">2025 한국연구재단 우수연구자 선정 (박효주 연구원)</td>
  <td class="px-6 py-4 text-base text-center"></td>
  <td class="px-6 py-4 text-base text-gray-600 dark:text-gray-400 text-center">2025-11-15</td>
</tr>
```

### 예시 2: 수상 소식 (링크 포함)

```html
<tr class="news-item hover:bg-gray-50 dark:hover:bg-gray-800/30 transition-colors">
  <td class="px-6 py-4 text-base text-gray-600 dark:text-gray-400 text-center">36</td>
  <td class="px-6 py-4 text-base text-gray-900 dark:text-white">2025 국제학술대회 최우수논문상 수상 (윤유정 박사과정)</td>
  <td class="px-6 py-4 text-base text-center">
    <a href="https://conference.example.com/award" target="_blank" class="inline-flex items-center gap-1 text-accent hover:text-blue-700 transition-colors">
      <span class="material-symbols-outlined text-base">link</span>
      Link
    </a>
  </td>
  <td class="px-6 py-4 text-base text-gray-600 dark:text-gray-400 text-center">2025-10-20</td>
</tr>
```

### 예시 3: 논문 게재 소식

```html
<tr class="news-item hover:bg-gray-50 dark:hover:bg-gray-800/30 transition-colors">
  <td class="px-6 py-4 text-base text-gray-600 dark:text-gray-400 text-center">37</td>
  <td class="px-6 py-4 text-base text-gray-900 dark:text-white">Remote Sensing 저널 논문 게재: AI-based Wildfire Detection (정예민 박사과정)</td>
  <td class="px-6 py-4 text-base text-center">
    <a href="https://doi.org/10.3390/rs13010001" target="_blank" class="inline-flex items-center gap-1 text-accent hover:text-blue-700 transition-colors">
      <span class="material-symbols-outlined text-base">link</span>
      Link
    </a>
  </td>
  <td class="px-6 py-4 text-base text-gray-600 dark:text-gray-400 text-center">2025-09-05</td>
</tr>
```

---

## 🔢 뉴스 번호 매기기

### 규칙
- **최신 뉴스가 가장 큰 번호**를 가집니다
- 새 뉴스 추가 시: 기존 최대 번호 + 1

### 예시
- 현재 최신 뉴스 번호: 33
- 새 뉴스 추가: 34번 사용

```html
<!-- 새 뉴스 (34번) -->
<tr class="news-item ...">
  <td ...>34</td>
  <td ...>새로운 소식</td>
  ...
</tr>

<!-- 기존 뉴스 (33번) -->
<tr class="news-item ...">
  <td ...>33</td>
  <td ...>이전 소식</td>
  ...
</tr>
```

---

## 📌 주의사항

### 1. 최신 뉴스는 맨 위에 추가
```html
<tbody class="divide-y ...">
  <!-- ✅ 여기에 새 뉴스 추가 (맨 위) -->
  <tr class="news-item ...">
    <td ...>34</td>  <!-- 새 뉴스 -->
    ...
  </tr>
  
  <tr class="news-item ...">
    <td ...>33</td>  <!-- 기존 뉴스 -->
    ...
  </tr>
  ...
</tbody>
```

### 2. 날짜 형식 준수
- **형식**: YYYY-MM-DD
- **예시**: 2025-12-25 (O), 2025/12/25 (X), 12-25-2025 (X)

### 3. 링크가 없으면 비워두기
```html
<td class="px-6 py-4 text-base text-center"></td>
```

### 4. 특수문자 처리
- HTML에서 특수문자는 이스케이프 필요:
  - `&` → `&amp;`
  - `<` → `&lt;`
  - `>` → `&gt;`

---

## 🗑️ 뉴스 삭제하기

### 1단계: 삭제할 뉴스 항목 찾기

### 2단계: `<tr>` 태그 전체 삭제

```html
<!-- 이 부분 전체 삭제 -->
<tr class="news-item hover:bg-gray-50 dark:hover:bg-gray-800/30 transition-colors">
  <td class="px-6 py-4 text-base text-gray-600 dark:text-gray-400 text-center">25</td>
  <td class="px-6 py-4 text-base text-gray-900 dark:text-white">삭제할 뉴스</td>
  <td class="px-6 py-4 text-base text-center"></td>
  <td class="px-6 py-4 text-base text-gray-600 dark:text-gray-400 text-center">2024-05-10</td>
</tr>
<!-- 여기까지 -->
```

---

## ✏️ 뉴스 수정하기

### 제목 수정
```html
<td class="px-6 py-4 text-base text-gray-900 dark:text-white">
  수정된 새로운 제목
</td>
```

### 링크 추가/변경
```html
<td class="px-6 py-4 text-base text-center">
  <a href="https://new-link.com" target="_blank" class="inline-flex items-center gap-1 text-accent hover:text-blue-700 transition-colors">
    <span class="material-symbols-outlined text-base">link</span>
    Link
  </a>
</td>
```

### 날짜 수정
```html
<td class="px-6 py-4 text-base text-gray-600 dark:text-gray-400 text-center">
  2025-12-31
</td>
```

---

## 🔍 페이지네이션

`news.html`은 페이지당 **10개의 뉴스**를 표시합니다.
- 뉴스가 10개 이하: 페이지네이션 없음
- 뉴스가 11개 이상: 자동으로 페이지 버튼 생성

**JavaScript가 자동으로 처리**하므로 수정할 필요 없습니다!

---

## 🧪 테스트 방법

### 1단계: HTML 구문 확인
- 태그가 올바르게 닫혔는지 확인
- 쌍따옴표가 짝을 이루는지 확인

### 2단계: 브라우저에서 확인
1. `news.html` 페이지를 엽니다
2. 새로 추가한 뉴스가 맨 위에 표시되는지 확인
3. 링크가 올바르게 작동하는지 확인
4. 페이지네이션이 정상 작동하는지 확인

### 3단계: 반응형 확인
- 브라우저 창 크기를 조절하여 모바일/태블릿에서도 잘 보이는지 확인

---

## 🆘 문제 해결

### 뉴스가 표시되지 않아요
1. ✅ `<tr>` 태그가 올바르게 닫혔는지 확인
2. ✅ `class="news-item"`이 있는지 확인
3. ✅ `<tbody>` 태그 안에 있는지 확인

### 레이아웃이 깨졌어요
1. ✅ 테이블 구조가 일정한지 확인 (4개의 `<td>` 유지)
2. ✅ HTML 태그가 올바르게 닫혔는지 확인

### 링크가 작동하지 않아요
1. ✅ URL이 정확한지 확인
2. ✅ `target="_blank"` 속성이 있는지 확인
3. ✅ `<a>` 태그가 올바르게 작성되었는지 확인

---

## 📂 파일 위치

```
news.html              ← 여기서 수정!
```

---

## 💡 팁

### 대량 추가 시
- 템플릿을 복사하여 여러 개를 한 번에 작성
- 번호는 순차적으로 증가
- 날짜순으로 정렬

### 백업하기
- 수정 전에 `news.html` 파일을 복사해두세요!

### 일관성 유지
- 제목 스타일을 일관되게 유지
- 날짜 형식을 통일
- 링크 텍스트를 "Link"로 통일

---

**HTML 태그 실수에 주의하세요! 페이지가 깨질 수 있습니다.**

