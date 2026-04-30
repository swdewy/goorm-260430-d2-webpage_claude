# 유유노마드 브랜딩 페이지

AI 크리에이터 · 디지털 노마드 **유유노마드(YuyuNomad)**의 개인 브랜딩 1페이지 웹사이트.

---

## 파일 구조

```
goorm-260430-d1-webpage_claude/
├── index.html                  ← 메인 페이지 (CSS · JS 포함 단일 파일)
├── 유유_3D_오리지널_Master.JPG  ← 캐릭터 이미지
├── README.md
├── CLAUDE.md                   ← 프로젝트 컨텍스트
└── project_brief.md            ← 작업 지시서
```

---

## 페이지 구성 (6섹션)

| 섹션 | 내용 |
|------|------|
| Hero | 메인 카피 + 캐릭터 이미지 + CTA 버튼 |
| About | 소개 텍스트 + 키워드 태그 + 프로필 카드 |
| Content | AI 콘텐츠 · 라이프 로그 · 교육 인사이트 3카드 |
| Philosophy | 다크 배경 역배색, 핵심 철학 2개 인용구 |
| Works | 유튜브 · 블로그 · 프로젝트 채널 3카드 |
| Contact | 구독 뉴스레터 + 협업 문의 2분할 CTA |

---

## 기술 스택

- **언어**: HTML · CSS · JavaScript (단일 파일)
- **폰트**: Google Fonts CDN
  - Noto Serif KR (헤드라인)
  - Noto Sans KR (본문)
  - IBM Plex Mono (태그 · 레이블)
- **애니메이션**: Intersection Observer API (스크롤 fade-up)
- **반응형**: 모바일 우선, 3열 그리드 → 1열 전환 (768px 이하)

---

## 컬러 시스템

| 역할 | 값 |
|------|----|
| 배경 | `#F5F0E8` 크림 베이지 |
| 포인트 | `#C4857A` 더스티 로즈 |
| 포인트 다크 | `#A06B62` 딥 로즈 |
| 텍스트 메인 | `#2C2420` 다크 브라운 |
| 텍스트 서브 | `#7A6E6A` 미디엄 브라운 |
| 카드 배경 | `#FFFFFF` |
| 보더 | `#E8DDD8` |

---

## 로컬 실행

별도 빌드 불필요. `index.html`을 브라우저에서 바로 열거나, 정적 서버로 실행:

```bash
npx serve .
```
