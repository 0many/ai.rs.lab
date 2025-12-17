# 👥 Members 추가/수정 가이드

## 📌 개요
`members.html` 페이지는 **JSON 파일 기반**으로 동작합니다.
멤버 추가/수정/삭제는 `members/data/members-data.json` 파일만 수정하면 됩니다!

---

## ✅ 장점
- ✨ **간단한 수정**: HTML 태그 없이 JSON만 수정
- 🎯 **에러 최소화**: 구조화된 데이터로 실수 방지
- 🔄 **일관성 유지**: 모든 카드가 동일한 디자인
- 📝 **가독성 향상**: 데이터가 깔끔하게 정리됨

---

## 📝 멤버 추가하기

### 1단계: JSON 파일 열기
`members/data/members-data.json` 파일을 에디터로 엽니다.

### 2단계: 적절한 섹션 찾기
멤버를 추가할 섹션을 선택합니다:
- **researchers**: 연구원 (Research Professor, Researcher, Engineer 등)
- **phd_students**: 박사과정
- **masters_students**: 석사과정
- **undergrad_students**: 학부생

### 3단계: 멤버 데이터 추가

다음 템플릿을 복사해서 정보를 채워넣으세요:

```json
{
  "name": "Hong Gildong",
  "title": "Master's Candidate",
  "email": "hong@pukyong.ac.kr",
  "photo": "member/증명사진/홍길동.jpg",
  "interests": ["AI-based Image Processing", "Computer Vision"]
}
```

#### 📋 각 필드 설명

| 필드 | 필수 | 설명 | 예시 |
|------|------|------|------|
| `name` | ✅ | 영문 이름 | "Jiah Jang" |
| `title` | ✅ | 직책/학위과정 | "Ph.D. Candidate" |
| `email` | ✅ | 이메일 주소 | "jiah@pukyong.ac.kr" |
| `photo` | ❌ | 사진 경로 (없으면 `null`) | "member/증명사진/장지아.jpg" |
| `interests` | ✅ | 연구 관심분야 배열 | ["AI", "Remote Sensing"] |
| `github` | ❌ | GitHub 링크 (선택) | "https://github.com/username" |
| `cv` | ❌ | CV 파일 링크 (선택) | "member/CV/이름_CV.pdf" |

### 4단계: 올바른 위치에 추가하기

**⚠️ 중요**: JSON 문법을 정확히 지켜야 합니다!

#### ✅ 올바른 예시 (배열 끝에 추가)

```json
{
  "researchers": [
    {
      "name": "Existing Member",
      ...
    },
    {
      "name": "New Member",
      "title": "Researcher",
      "email": "new@pukyong.ac.kr",
      "photo": "member/증명사진/new.jpg",
      "interests": ["AI", "Deep Learning"]
    }
  ]
}
```

**주의**: 마지막 항목에는 쉼표(`,`)를 붙이지 않습니다!

---

## 🔄 멤버 정보 수정하기

### 1단계: JSON 파일에서 수정할 멤버 찾기
`members/data/members-data.json`에서 수정할 멤버의 `name`으로 검색합니다.

### 2단계: 원하는 필드 수정
```json
{
  "name": "Jiah Jang",
  "title": "Ph.D. Candidate",  // ← 이 부분을 수정
  "email": "new.email@pukyong.ac.kr",  // ← 이메일 변경
  "photo": "member/증명사진/장지아_new.jpg",  // ← 새 사진
  "interests": ["New Interest", "Another Interest"]  // ← 관심분야 업데이트
}
```

### 3단계: 저장 후 브라우저 새로고침

---

## ❌ 멤버 삭제하기

### 1단계: JSON 파일에서 삭제할 멤버 찾기

### 2단계: 해당 멤버의 전체 블록 삭제
```json
{
  "researchers": [
    {
      "name": "Keep This Member",
      ...
    },
    // ← 여기서부터
    {
      "name": "Delete This Member",
      "title": "Researcher",
      ...
    },
    // ← 여기까지 삭제
    {
      "name": "Keep This Member Too",
      ...
    }
  ]
}
```

**⚠️ 주의**: 삭제 후 쉼표(`,`)가 올바르게 유지되는지 확인하세요!

---

## 👨‍🎓 Alumni 추가하기

Alumni는 단순 문자열 배열입니다.

### Ph.D. Alumni 추가

```json
{
  "alumni": {
    "phd": [
      "김나리(2018), 국립부경대학교",
      "새로운 졸업생(2025), 회사명"  // ← 새 항목 추가
    ],
    "masters": [...]
  }
}
```

### M.S. Alumni 추가

```json
{
  "alumni": {
    "phd": [...],
    "masters": [
      "이하정(2012), BNK시스템",
      "새로운 졸업생(2025), 회사명"  // ← 새 항목 추가
    ]
  }
}
```

---

## 📸 사진 추가하기

### 1단계: 사진 파일 준비
- **위치**: `member/증명사진/` 폴더
- **파일명**: 한글 또는 영문 (예: `홍길동.jpg`, `hong.jpg`)
- **형식**: JPG, PNG

### 2단계: JSON에 경로 입력
```json
{
  "photo": "member/증명사진/홍길동.jpg"
}
```

### 사진이 없는 경우
```json
{
  "photo": null
}
```
→ 자동으로 기본 아이콘(👤)이 표시됩니다.

---

## 🔗 GitHub 링크 추가하기

```json
{
  "name": "Jaeung Sim",
  "title": "Researcher",
  "email": "tlawodnd1325@naver.com",
  "photo": "member/증명사진/심재웅.jpg",
  "interests": ["Vision-Language Model", "Computer Vision"],
  "github": "https://github.com/simjw0223?tab=repositories"
}
```

---

## 📄 CV 링크 추가하기

### 1단계: CV 파일 업로드
CV 파일을 `member/CV/` 폴더에 업로드합니다.

### 2단계: JSON에 경로 추가
```json
{
  "name": "Youjeong Youn",
  "title": "Ph.D. Candidate",
  "email": "dbwjd0757@pukyong.ac.kr",
  "photo": "member/증명사진/윤유정.png",
  "interests": ["..."],
  "cv": "member/CV/윤유정_CV.pdf"
}
```

---

## ⚠️ JSON 문법 주의사항

### ✅ DO (올바른 사용)
```json
{
  "name": "Hong Gildong",
  "interests": ["AI", "Deep Learning"],
  "github": "https://github.com/hong"
}
```

### ❌ DON'T (잘못된 사용)

#### 1. 마지막 항목에 쉼표 사용
```json
{
  "name": "Hong",
  "email": "hong@test.com",  // ← 마지막에 쉼표 금지!
}
```

#### 2. 쌍따옴표 빠뜨림
```json
{
  name: "Hong",  // ❌ 키는 반드시 쌍따옴표로!
  "email": hong@test.com  // ❌ 값도 쌍따옴표로!
}
```

#### 3. 배열 문법 오류
```json
{
  "interests": "AI"  // ❌ 배열은 []로!
}
```

**올바른 사용:**
```json
{
  "interests": ["AI"]  // ✅
}
```

---

## 🧪 테스트 방법

### 1단계: JSON 유효성 검사
- [JSONLint](https://jsonlint.com/)에서 JSON 파일 내용을 붙여넣어 문법 오류 확인

### 2단계: 브라우저에서 확인
1. `members.html` 페이지를 엽니다
2. 브라우저 개발자 도구(F12)를 엽니다
3. Console 탭에서 에러 메시지 확인
4. 각 탭(Researchers, Ph.D., M.S. 등)을 클릭하여 정상 작동 확인

### 3단계: 새로고침
변경사항이 반영되지 않으면 **Ctrl + Shift + R** (강력 새로고침)

---

## 🆘 문제 해결

### 멤버가 표시되지 않아요
1. ✅ JSON 파일 경로가 올바른지 확인
2. ✅ JSON 문법 오류 확인 (JSONLint 사용)
3. ✅ 브라우저 콘솔에서 에러 메시지 확인
4. ✅ 사진 파일 경로가 올바른지 확인

### 사진이 표시되지 않아요
1. ✅ 사진 파일이 `member/증명사진/` 폴더에 있는지 확인
2. ✅ JSON의 `photo` 경로가 정확한지 확인
3. ✅ 파일 이름 대소문자 확인 (Windows는 무시하지만 서버는 구분!)

### JSON 저장 후에도 변경사항이 안 보여요
1. ✅ **Ctrl + Shift + R** (강력 새로고침)
2. ✅ 브라우저 캐시 삭제
3. ✅ JSON 파일이 올바르게 저장되었는지 확인

---

## 📂 파일 구조

```
members/
  data/
    members-data.json        ← 멤버 데이터 (여기만 수정!)
  증명사진/
    김나리.jpg
    장지아.jpg
    ...
  CV/
    윤유정_CV.pdf
    ...

members.html                 ← 웹페이지 (수정 금지)
```

---

## 💡 팁

### 멤버 순서 변경하기
JSON 배열에서 항목의 순서를 바꾸면 페이지에서도 순서가 바뀝니다.

### 여러 멤버 한 번에 추가하기
JSON 파일에서 배열 안에 여러 개의 객체를 추가하면 됩니다.

### 백업하기
수정 전에 `members-data.json` 파일을 복사해두세요!

---

**문제가 발생하면 JSON 파일의 문법 오류를 먼저 확인하세요!**

