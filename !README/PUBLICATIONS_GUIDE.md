# 📚 Publications 추가/수정 가이드

## 📌 개요
`publications.html` 파일은 연구실의 논문(Journal)과 특허(Patent) 정보를 관리합니다.
이 가이드를 따라 새로운 논문이나 특허를 쉽게 추가하실 수 있습니다.

---

## 📝 Journal (논문) 추가하기

### 1단계: publications.html 파일 열기
`publications.html` 파일을 에디터로 엽니다.

### 2단계: International vs Domestic 선택
- **International Journal**: `<!-- ==================== International Journal 탭 내용 ==================== -->` 섹션
- **Domestic Journal**: `<!-- ==================== Domestic Journal 탭 내용 ==================== -->` 섹션

### 3단계: 연도 섹션 찾기 또는 추가하기

#### 기존 연도가 있는 경우
해당 연도의 `<div class="space-y-3">` 내부에 새 논문을 추가합니다.

#### 새로운 연도 추가하는 경우
```html
<!-- ==================== 2026년 논문 ==================== -->
<div>
  <h3 class="text-4xl font-bold mb-6 text-accent">2026</h3>
  <div class="space-y-3">
    
    <!-- 여기에 논문 아이템 추가 -->
    
  </div>
</div>
```

### 4단계: 논문 아이템 추가하기

다음 템플릿을 복사해서 정보를 채워넣으세요:

```html
<!-- ========== Paper 번호 ========== -->
<div class="paper-item pb-3 border-b border-gray-200 dark:border-gray-700 relative">
  <div class="flex items-start gap-4">
    <span class="text-base font-bold text-gray-400 dark:text-gray-500 flex-shrink-0 mt-1">번호</span>
    <div class="flex-grow w-full">
      <h4 class="text-lg font-bold text-primary-dark dark:text-white mb-2 w-full break-words">논문 제목</h4>
      <p class="text-sm text-gray-600 dark:text-gray-400"><i>저널명</i>, 연도</p>
    </div>
  </div>
  <a href="https://doi.org/논문DOI주소" class="absolute bottom-2 right-0 flex items-center gap-1 text-accent hover:text-blue-700 transition-colors text-sm font-medium" target="_blank">
    <span class="material-symbols-outlined text-base">link</span>
    Link
  </a>
</div>
```

### 5단계: 정보 입력하기
- **번호**: 논문 일련번호 (예: 58)
- **논문 제목**: 영문 논문 제목
- **저널명**: 학술지 이름 (이탤릭체로 표시됨)
- **연도**: 출판 연도
- **DOI 주소**: 논문의 DOI 링크 (예: https://doi.org/10.1007/s12303-025-00049-w)

### 📋 예시

```html
<!-- ========== Paper 59 ========== -->
<div class="paper-item pb-3 border-b border-gray-200 dark:border-gray-700 relative">
  <div class="flex items-start gap-4">
    <span class="text-base font-bold text-gray-400 dark:text-gray-500 flex-shrink-0 mt-1">59</span>
    <div class="flex-grow w-full">
      <h4 class="text-lg font-bold text-primary-dark dark:text-white mb-2 w-full break-words">Deep Learning for Satellite Image Analysis</h4>
      <p class="text-sm text-gray-600 dark:text-gray-400"><i>Remote Sensing</i>, 2025</p>
    </div>
  </div>
  <a href="https://doi.org/10.3390/rs13010001" class="absolute bottom-2 right-0 flex items-center gap-1 text-accent hover:text-blue-700 transition-colors text-sm font-medium" target="_blank">
    <span class="material-symbols-outlined text-base">link</span>
    Link
  </a>
</div>
```

---

## 🔬 Patent (특허) 추가하기

### 1단계: Patent 섹션 찾기
`<!-- ==================== Patent 섹션 ==================== -->` 부분으로 이동합니다.

### 2단계: 연도 섹션 찾기 또는 추가하기

#### 기존 연도가 있는 경우
해당 연도의 `<div class="space-y-3">` 내부에 새 특허를 추가합니다.

#### 새로운 연도 추가하는 경우
```html
<!-- ==================== 2025년 특허 ==================== -->
<div>
  <h3 class="text-4xl font-bold mb-6 text-accent">2025</h3>
  <div class="space-y-3">
    
    <!-- 여기에 특허 아이템 추가 -->
    
  </div>
</div>
```

### 3단계: 특허 아이템 추가하기

다음 템플릿을 복사해서 정보를 채워넣으세요:

```html
<!-- ========== Patent 번호 ========== -->
<div class="pb-3 border-b border-gray-200 dark:border-gray-700">
  <div class="flex items-start gap-4">
    <span class="text-base font-bold text-gray-400 dark:text-gray-500 flex-shrink-0 mt-1">번호</span>
    <div class="flex-grow w-full">
      <h4 class="text-lg font-bold text-primary-dark dark:text-white mb-2 w-full break-words">특허명</h4>
      <p class="text-sm text-gray-600 dark:text-gray-400">등록번호: 특허등록번호</p>
    </div>
  </div>
</div>
```

### 4단계: 정보 입력하기
- **번호**: 특허 일련번호 (예: 4)
- **특허명**: 특허 이름 (한글 또는 영문)
- **특허등록번호**: 등록번호 (예: 10-1767568)

### 📋 예시

```html
<!-- ========== Patent 4 ========== -->
<div class="pb-3 border-b border-gray-200 dark:border-gray-700">
  <div class="flex items-start gap-4">
    <span class="text-base font-bold text-gray-400 dark:text-gray-500 flex-shrink-0 mt-1">4</span>
    <div class="flex-grow w-full">
      <h4 class="text-lg font-bold text-primary-dark dark:text-white mb-2 w-full break-words">인공지능 기반 위성영상 분석 시스템</h4>
      <p class="text-sm text-gray-600 dark:text-gray-400">등록번호: 10-2345678</p>
    </div>
  </div>
</div>
```

---

## ⚠️ 주의사항

1. **논문/특허 번호는 최신순으로 증가**합니다 (가장 최근 논문이 가장 큰 번호)
2. **연도 섹션은 내림차순**으로 정렬됩니다 (최신 연도가 위쪽)
3. **HTML 구조를 정확히 유지**해주세요 (들여쓰기, 닫는 태그 등)
4. **DOI 링크가 없는 경우** `<a>` 태그 전체를 삭제하면 됩니다
5. **특수문자**는 HTML 엔티티로 변환해야 할 수 있습니다
   - `&` → `&amp;`
   - `<` → `&lt;`
   - `>` → `&gt;`

---

## 🔍 추가 정보 위치

### International Journal 섹션
- **위치**: Line ~700 근처
- **섹션 시작**: `<!-- ==================== International Journal 탭 내용 ==================== -->`

### Domestic Journal 섹션
- **위치**: International Journal 섹션 아래
- **섹션 시작**: `<!-- ==================== Domestic Journal 탭 내용 ==================== -->`

### Patent 섹션
- **위치**: Line ~3654 근처
- **섹션 시작**: `<!-- ==================== Patent 섹션 ==================== -->`

---

## ✅ 수정 후 확인사항

1. ✅ 브라우저에서 `publications.html` 페이지 열기
2. ✅ Journal 탭에서 새 논문이 올바르게 표시되는지 확인
3. ✅ Patent 탭에서 새 특허가 올바르게 표시되는지 확인
4. ✅ 링크 클릭 시 올바른 페이지로 이동하는지 확인
5. ✅ 다크 모드에서도 정상 표시되는지 확인

---

**문제가 발생하면 주석(`<!-- -->`)을 확인하여 올바른 섹션에 추가했는지 확인하세요!**

