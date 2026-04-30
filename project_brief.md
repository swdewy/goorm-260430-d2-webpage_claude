# 유유노마드 브랜딩 페이지 — 작업 지시서

## 목표
유유노마드의 개인 브랜딩 1페이지 웹사이트를 HTML/CSS/JS로 제작한다.
슬라이드 덱(AI_Shorts_Factory.pdf) 의 디자인 무드를 웹으로 자연스럽게 전환하는 것이 핵심.

---

## 즉시 시작할 작업

```
index.html 단일 파일로 제작 (외부 CSS/JS 파일 분리 없이)
Google Fonts CDN 사용 (Noto Serif KR, Noto Sans KR, IBM Plex Mono)
반응형 (모바일 우선)
스크롤 애니메이션 (Intersection Observer API 사용)
```

---

## 파일 구조
```
yuyu_nomad/
├── CLAUDE.md          ← 프로젝트 컨텍스트 (이 파일)
├── project_brief.md   ← 작업 지시서 (현재 파일)
├── index.html         ← 메인 페이지 (제작 대상)
└── assets/
    └── yuyu_character.jpg  ← 캐릭터 이미지 (직접 추가 필요)
```

---

## 컴포넌트별 상세 스펙

### 공통 컴포넌트
```css
/* 섹션 공통 */
padding: 80px 24px;
max-width: 1080px;
margin: 0 auto;

/* 카드 */
background: #FFFFFF;
border: 1px solid #E8DDD8;
border-radius: 16px;
padding: 24px;

/* 버튼 Primary */
background: #C4857A;
color: white;
border-radius: 100px;
padding: 12px 24px;
font-size: 14px;

/* 버튼 Outline */
background: transparent;
border: 1.5px solid #C4857A;
color: #C4857A;
border-radius: 100px;
```

### Hero 섹션
- 레이아웃: `display: flex; justify-content: space-between; align-items: center;`
- 캐릭터 이미지: 우측, 너비 280px
- 메인 타이틀: Noto Serif KR, 36px, weight 300
- 강조 단어 ("설계"): color #C4857A
- 서브타이틀: 18px, color #7A6E6A
- 본문: 15px, line-height 1.9
- CTA 버튼 2개 (Primary + Outline)

### About 섹션
- 배경: #F5F0E8
- 헤드라인: Noto Serif KR, 22px
- 키워드 태그: 작은 pill 형태, background #E8DDD8

### Content 섹션 (3카드 그리드)
- `display: grid; grid-template-columns: repeat(3, 1fr); gap: 16px;`
- 각 카드: 아이콘(이모지) + 제목 + 설명 + 태그들
- 아이콘 배경: 각각 다른 파스텔 계열

### Philosophy 섹션
- 배경: #2C2420 (다크 브라운, 역배색)
- 텍스트: #F5F0E8
- 인용구 스타일: 좌측 border-left 3px solid #C4857A
- 인용구 폰트: Noto Serif KR, italic

### Works 섹션
- 배경: #F5F0E8
- 3카드 그리드
- 각 카드에 채널 링크 버튼 포함

### Contact 섹션
- 배경: #C4857A (포인트 컬러 풀배경)
- 텍스트: white
- 2분할 레이아웃: 구독 | 협업문의

---

## 애니메이션 스펙
```javascript
// 스크롤 진입 시 카드 페이드업
const observer = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      entry.target.classList.add('visible');
    }
  });
}, { threshold: 0.1 });

// CSS
.fade-up {
  opacity: 0;
  transform: translateY(24px);
  transition: opacity 0.6s ease, transform 0.6s ease;
}
.fade-up.visible {
  opacity: 1;
  transform: translateY(0);
}
```

---

## 주의사항
1. 슬라이드 밀도 유지 — 텍스트 과도하게 늘리지 말 것
2. 캐릭터 이미지(yuyu_character.jpg)는 assets 폴더에 직접 추가 필요
3. 실제 링크(유튜브, 블로그 URL)는 `#` placeholder로 처리
4. 모바일에서 3열 그리드 → 1열로 전환

---

## 첫 번째 작업 명령
> `index.html` 파일을 위 스펙대로 완성해줘.
> 캐릭터 이미지는 `./assets/yuyu_character.jpg` 경로로 참조.
> 단일 HTML 파일로 CSS, JS 모두 포함해서 작성.
