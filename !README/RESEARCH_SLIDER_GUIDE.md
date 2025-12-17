# 연구분야 슬라이더 이미지 추가 가이드

## 📌 개요
Research 페이지의 슬라이더에 새로운 연구분야 이미지를 추가하는 방법을 안내합니다.

**🎯 핵심:** 이미지는 **`research/sections/` 폴더의 파일 하나만 수정**하면 모든 페이지에 자동 반영됩니다!

---

## 🗂️ 새로운 파일 구조

```
📁 프로젝트/
  ├─ 1_Research.html              (Remote Sensing 페이지)
  ├─ 2_Research.html              (AI Monitoring 페이지)
  ├─ 3_Research.html              (Geospatial Fusion 페이지)
  └─ research/
      ├─ 산불피해지.png           (이미지 파일들)
      ├─ 산불피해지2.png
      ├─ 산불피해지3.png
      └─ sections/                (🆕 슬라이더 공통 파일)
          ├─ remote-sensing-slider.html
          ├─ ai-monitoring-slider.html
          └─ geospatial-fusion-slider.html
```

**✅ 장점:**
- 이미지 추가 시 **한 파일만 수정**
- 모든 Research 페이지에 **자동 반영**
- 중복 코드 제거로 관리 쉬움

---

## 🚀 빠른 시작

### 1️⃣ 이미지 파일 준비
```
📁 research/
  ├── 산불피해지2.png  (기존)
  ├── 산불피해지3.png  (기존)
  └── 새이미지.png      (← 여기에 추가)
```

### 2️⃣ 어느 섹션에 추가할지 결정
- **Remote Sensing** → `research/sections/remote-sensing-slider.html`
- **AI Monitoring** → `research/sections/ai-monitoring-slider.html`
- **Geospatial Fusion** → `research/sections/geospatial-fusion-slider.html`

### 3️⃣ 해당 슬라이더 파일 열기
예: AI Monitoring에 이미지 추가하려면 `ai-monitoring-slider.html` 열기

### 4️⃣ 이미지 추가 영역 찾기
파일에서 다음 주석을 찾으세요:
```html
<!-- ========== 여기에 새로운 이미지를 추가하세요 ========== -->
```

### 5️⃣ 이미지 태그 복사 & 붙여넣기
아래 템플릿을 복사하여 추가 영역에 붙여넣으세요:

```html
<img src="research/새이미지.png"
     alt="이미지 설명"
     class="research-slide hidden"
     oncontextmenu="return false;" ondragstart="return false;" onselectstart="return false;"/>
```

### 6️⃣ 수정 사항
- `src="research/새이미지.png"` → 실제 파일명으로 변경
- `alt="이미지 설명"` → 이미지에 대한 간단한 설명

### 7️⃣ 저장 & 확인
- 파일 저장 후 브라우저 새로고침 (Ctrl+Shift+R)
- **모든 Research 페이지에 자동 반영됨!** ✨

---

## 🎯 핵심 포인트

### ⚡ 한 파일만 수정하면 끝!

```
ai-monitoring-slider.html 수정
         ↓
1_Research.html  ✅ 자동 반영
2_Research.html  ✅ 자동 반영
3_Research.html  ✅ 자동 반영
```

**이전 방식:** 3개 파일 모두 수정 필요 😫  
**현재 방식:** 1개 파일만 수정 😊

---

## 📖 상세 가이드

### 전체 구조 이해하기

```html
<div class="research-slider-container">
  
  <!-- [1] 이전 버튼 -->
  <button type="button" class="research-slide-btn research-prev">
    <span class="material-symbols-outlined text-2xl">chevron_left</span>
  </button>
  
  <!-- [2] 첫 번째 이미지 (기본으로 보임) -->
  <img src="research/이미지1.png"
       alt="설명1"
       class="research-slide"
       oncontextmenu="return false;" ondragstart="return false;" onselectstart="return false;"/>
  
  <!-- [3] 추가 이미지들 (hidden 상태) -->
  <img src="research/이미지2.png"
       alt="설명2"
       class="research-slide hidden"
       oncontextmenu="return false;" ondragstart="return false;" onselectstart="return false;"/>
  
  <!-- [4] 다음 버튼 -->
  <button type="button" class="research-slide-btn research-next">
    <span class="material-symbols-outlined text-2xl">chevron_right</span>
  </button>
  
</div>
```

### 핵심 포인트

#### ✅ DO (해야 할 것)
1. **항상 `class="research-slide hidden"` 포함** (첫 번째 제외)
2. **버튼 사이에만 이미지 추가**
3. **`alt` 속성에 의미있는 설명 작성**
4. **파일 경로는 `research/` 폴더 기준**

#### ❌ DON'T (하지 말아야 할 것)
1. 첫 번째 이미지에 `hidden` 추가하지 않기
2. 버튼의 위치나 순서 변경하지 않기
3. `class="research-slide"` 삭제하지 않기
4. 이미지 보호 속성(`oncontextmenu` 등) 제거하지 않기

---

## 🎯 실전 예제

### 예제: AI Monitoring에 이미지 3개 추가

**파일**: `research/sections/ai-monitoring-slider.html`

```html
<!-- ========== 기존 이미지 ========== -->
<img src="research/산불피해지2.png"
     alt="Wildfire Burned Area"
     class="research-slide"
     oncontextmenu="return false;" ondragstart="return false;" onselectstart="return false;"/>

<img src="research/산불피해지3.png"
     alt="Wildfire Damage Analysis"
     class="research-slide hidden"
     oncontextmenu="return false;" ondragstart="return false;" onselectstart="return false;"/>

<!-- ========== 여기에 새로운 이미지를 추가하세요 ========== -->

<!-- 🆕 새로 추가하는 이미지들 -->
<img src="research/산불연기감지.png"
     alt="Wildfire Smoke Detection"
     class="research-slide hidden"
     oncontextmenu="return false;" ondragstart="return false;" onselectstart="return false;"/>

<img src="research/산불예측모델.png"
     alt="Wildfire Prediction Model"
     class="research-slide hidden"
     oncontextmenu="return false;" ondragstart="return false;" onselectstart="return false;"/>

<img src="research/실시간모니터링.png"
     alt="Real-time Monitoring System"
     class="research-slide hidden"
     oncontextmenu="return false;" ondragstart="return false;" onselectstart="return false;"/>

<!-- ========== 추가 영역 끝 ========== -->
```

**결과**: 
- ✅ 1_Research.html#ai-monitoring → 5개 이미지 표시
- ✅ 2_Research.html#ai-monitoring → 5개 이미지 표시  
- ✅ 3_Research.html#ai-monitoring → 5개 이미지 표시

**한 파일만 수정했지만 모든 페이지에 자동 반영!** 🎉

---

## 🔧 트러블슈팅

### Q1. 이미지가 보이지 않아요
**A.** 다음을 확인하세요:
- [ ] 파일이 `research/` 폴더에 있는지
- [ ] 파일명이 정확한지 (대소문자, 확장자 포함)
- [ ] `research/sections/` 폴더의 슬라이더 파일을 수정했는지
- [ ] 브라우저 캐시를 지웠는지 (Ctrl+Shift+R)

### Q2. 슬라이더가 작동하지 않아요
**A.** 다음을 확인하세요:
- [ ] `class="research-slide"`가 있는지
- [ ] 버튼들이 올바른 위치에 있는지
- [ ] JavaScript 오류가 있는지 (F12 개발자 도구 확인)
- [ ] 로컬 파일로 열었다면 서버를 통해 열어야 함 (CORS 문제)

### Q3. 첫 번째 이미지만 계속 보여요
**A.** 추가한 이미지에 `hidden` 클래스가 포함되어 있는지 확인하세요.

### Q4. 이미지를 삭제하고 싶어요
**A.** `research/sections/` 폴더의 해당 슬라이더 파일에서 `<img>` 태그를 통째로 삭제하면 됩니다.

### Q5. "슬라이더를 로드하는 중 오류가 발생했습니다" 메시지가 떠요
**A.** 로컬 파일 시스템에서는 CORS 제한으로 fetch가 작동하지 않을 수 있습니다:
- **해결 방법 1**: 로컬 서버를 실행하세요
  ```bash
  # Python 3
  python -m http.server 8000
  # 또는 Node.js
  npx serve
  ```
- **해결 방법 2**: Live Server (VS Code 확장) 사용
- **해결 방법 3**: GitHub Pages에 배포하여 테스트

---

## 📝 CSS 스타일 정보

슬라이더 관련 CSS는 `style.css`에 정의되어 있습니다:

```css
/* 슬라이더 컨테이너 */
.research-slider-container {
  max-width: 70%;    /* 이미지 너비 조절 */
}

/* 슬라이드 이미지 */
.research-slide {
  width: 100%;       /* 컨테이너에 꽉 차게 */
  height: auto;      /* 비율 유지 */
}

/* 버튼 스타일 */
.research-slide-btn {
  width: 2.5rem;     /* 버튼 크기 */
  height: 2.5rem;
}

.research-prev { left: -3rem; }   /* 왼쪽 버튼 위치 */
.research-next { right: -3rem; }  /* 오른쪽 버튼 위치 */
```

**스타일 변경이 필요하면 `style.css`를 수정하세요.**

---

## 🎨 커스터마이징

### 이미지 크기 조절
`style.css`에서 수정:
```css
.research-slider-container {
  max-width: 70%;  /* 50% ~ 90% 사이로 조절 가능 */
}
```

### 버튼 위치 조절
`style.css`에서 수정:
```css
.research-prev { left: -3rem; }   /* 더 멀리: -4rem, 더 가까이: -2rem */
.research-next { right: -3rem; }
```

### 버튼 크기 변경
`style.css`에서 수정:
```css
.research-slide-btn {
  width: 3rem;   /* 크게: 3rem, 작게: 2rem */
  height: 3rem;
}
```

---

## ✅ 체크리스트

이미지 추가 후 다음을 확인하세요:

- [ ] 이미지 파일이 `research/` 폴더에 있음
- [ ] 파일명이 HTML 코드와 정확히 일치함
- [ ] `class="research-slide hidden"` 포함됨 (첫 번째 제외)
- [ ] 이미지 보호 속성이 모두 포함됨
- [ ] 브라우저에서 정상 작동 확인
- [ ] 좌우 버튼으로 모든 이미지가 보이는지 확인

---

## 📞 도움이 필요하신가요?

문제가 계속되면:
1. 브라우저 콘솔(F12)에서 오류 메시지 확인
2. HTML 파일의 구조가 예제와 동일한지 확인
3. 캐시 삭제 후 재시도 (Ctrl+Shift+R)

---

## 📂 파일 구조 요약

```
프로젝트/
├─ research/
│   ├─ sections/                    👈 이미지를 추가할 때는 여기만 수정!
│   │   ├─ remote-sensing-slider.html
│   │   ├─ ai-monitoring-slider.html
│   │   └─ geospatial-fusion-slider.html
│   ├─ 산불피해지.png
│   ├─ 산불피해지2.png
│   └─ 산불피해지3.png
├─ 1_Research.html                  (자동으로 sections/ 로드)
├─ 2_Research.html                  (자동으로 sections/ 로드)
├─ 3_Research.html                  (자동으로 sections/ 로드)
└─ style.css                        (슬라이더 스타일 정의)
```

---

## 🎓 기술 상세

### 동작 원리

1. **페이지 로드 시**
   ```javascript
   fetch('research/sections/ai-monitoring-slider.html')
   ```
   
2. **HTML 삽입**
   ```javascript
   container.innerHTML = html;
   ```
   
3. **슬라이더 초기화**
   ```javascript
   initializeSlider();
   ```

### 왜 이렇게 했나요?

**문제**: 동일한 슬라이더 코드가 3개 파일에 중복  
**해결**: 공통 HTML을 외부 파일로 분리하여 한 곳에서 관리  
**장점**: 유지보수 쉬움, 중복 제거, 확장 가능

---

**마지막 업데이트**: 2024년 12월  
**관련 파일**: 
- `research/sections/*.html` (슬라이더 공통 파일)
- `1_Research.html`, `2_Research.html`, `3_Research.html` (메인 페이지)
- `style.css` (슬라이더 스타일)

