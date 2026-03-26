# 🐾 Hugroomer (허그루머) - All-in-One Pet Care SaaS

**"전문 미용사를 위한 최고의 운영 파트너"**  
애견미용샵 및 펫케어 비즈니스의 DX(Digital Transformation)를 위한 엔터프라이즈급 B2B SaaS 플랫폼입니다.
단순한 예약 관리를 넘어 AI 기반 리텐션 도구, 실시간 커뮤니케이션 인프라, 엔터프라이즈급 보안 아키텍처를 제공합니다.

> **"원장님은 미용에만 집중하세요, 나머지는 허그루머가 관리합니다."**  
> 본 프로젝트는 1인 개발로 기획, DB 설계, UI/UX, 백엔드 로직, 모바일 앱까지 전체 풀스택 과정을 수행하며 실제 상용 수준의 완성도를 목표로 개발되었습니다.

---

## 📸 UI Showcase (시각적 프리뷰)

*아래 이미지들은 서비스의 핵심 UI 구조를 나타내며, 실제 상용화 버전의 스크린샷으로 대체될 예정입니다.*

### 1. 엔터프라이즈 운영 대시보드 & 스마트 타임라인
![Dashboard & Timeline Preview](https://placehold.co/1200x600/6366f1/white?text=Enterprise+Dashboard+%26+Smart+Gantt+Timeline+UI)
* **운영 대시보드**: 매출 통계, 오늘 예약, 실시간 알림을 한눈에 파악할 수 있는 위젯 중심의 설계
* **Gantt 타임라인**: 80px 그리드 단위의 정밀한 시간축과 직원별 예약 겹침 방지 알고리즘이 적용된 스케줄러

### 2. AI 재방문 리텐션 엔진 (Claude 3.5 연동)
![AI Revisit Message UI](https://placehold.co/800x450/4f46e5/white?text=AI+Retention+Engine+-+Claude+3.5+Sonnet)
* **지능형 분석**: 반려동물의 마지막 방문일과 미용 스타일을 분석하여 3가지 톤(친근한, 정중한, 간단한)의 메시지 자동 생성

### 3. 올인원 케어 모듈 (호텔 & 유치원)
![Care Module UI](https://placehold.co/800x450/4338ca/white?text=Care+Module+-+Hotel+%26+Kindergarten+Management)
* **통합 관리**: 객실 가동률 시각화, AI 기반 돌봄 리포트 요약 및 전자 동의서 연동 화면

### 4. 보호자용 크로스 플랫폼 (Mobile App & PWA)
![Mobile App UI](https://placehold.co/600x400/3730a3/white?text=Guardian+Mobile+App+%26+PWA+UI)
* **심리스한 경험**: React Native 기반의 부드러운 인터랙션과 PWA를 통한 설치 없는 즉각적인 예약 환경 제공

---

## ✨ 주요 기능 및 비즈니스 가치

| 기능 | 설명 |
|---|---|
| **Enterprise Timeline** | **Greedy Column Assignment** 알고리즘을 적용하여 직원별 예약 겹침을 실시간으로 계산하고 시각화합니다. |
| **AI Retention Engine** | **Claude 3.5 Sonnet**을 활용하여 단순 예약 유도를 넘어, 각 반려동물의 미용 주기와 특성에 맞춘 초개인화 메시지를 생성합니다. |
| **Real-time Engine** | **Supabase Realtime** 기반의 채팅 및 인앱 알림 시스템을 통해 샵 내부 협업 효율을 극대화합니다. |
| **Smart Care Module** | 펫호텔, 유치원 등 복잡한 입/퇴실 프로세스를 자동화하고 AI 기반 돌봄 리포트를 제공합니다. |
| **Cross-Platform** | Next.js 14(Web)와 React Native(Mobile) 간의 코드 및 타입 공유를 통해 일관된 데이터 경험을 제공합니다. |

---

## 💻 Technical Stack & Architecture

### Framework & Language
- **Frontend**: Next.js 14 (App Router), React 18, TypeScript (Strict Mode)
- **Mobile**: React Native (Expo SDK 50+), New Architecture 기반 빌드
- **State Management**: TanStack Query (Server State), Server Actions (Mutation)
- **Styling**: TailwindCSS, Radix UI (Shadcn/ui 기반 커스텀)

### Backend & Cloud Native
- **Database**: PostgreSQL (Supabase)
- **Security**: Row Level Security (RLS) 기반 테넌트 격리
- **Storage**: Supabase Storage (미용 전/후 사진 고속 서빙)
- **Serverless**: Vercel Edge Functions (API & Cron Jobs)

### DevOps & Infrastructure
- **Monorepo**: **Turborepo**를 통한 패키지 관리 및 빌드 최적화
- **CI/CD**: GitHub Actions, Vercel, EAS (Expo Application Services)
- **Payments**: Toss Payments (Subscription Billing)

---

## 🏗️ Monorepo Directory Strategy

확장성과 코드 재사용성을 극대화하기 위해 모노레포 구조를 채택했습니다.

```text
hugroomer/
├── apps/
│   ├── web/          # Next.js 14 기반 미용샵 운영 대시보드 (B2B)
│   ├── mobile/       # React Native Expo 기반 보호자용 앱 (B2C)
│   └── landing/      # 서비스 소개 및 마케팅 페이지
├── packages/
│   ├── ui/           # 공통 디자인 시스템 (Shared Components)
│   ├── types/        # DB 스키마와 1:1 매칭되는 공통 TypeScript 타입 정의
│   └── utils/        # 날짜 연산, 포맷팅 등 순수 함수 유틸리티
└── supabase/
    ├── schema.sql    # Single Source of Truth (마스터 스키마)
    └── migrations/   # 버전 관리가 포함된 SQL 마이그레이션 전략
```

---

## ✅ Implementation Status (구현 현황)

현재 전체 공정률은 약 **87%**이며, 핵심 비즈니스 로직은 상용화 가능한 수준으로 구현되었습니다.

### 🏢 B2B 운영 대시보드 (Web)
- [x] **운영 허브**: 오늘 예약, 이번 달 매출 통계, 대기 예약 관리 및 실시간 알림 시스템
- [x] **스케줄 엔진**: 직원별 Gantt 차트 타임라인 및 실시간 예약 겹침 감지/경고 로직
- [x] **고객 관리**: 반려동물별 미용 이력 스냅샷, 블랙리스트(3단계) 및 노쇼 관리
- [x] **AI 비즈니스**: Claude 3.5 기반 재방문 문자 초안 생성 및 케어 리포트 자동 요약
- [x] **케어 모듈**: 펫호텔/유치원 전용 공간 관리, 체크인/아웃 프로세스 및 돌봄 일지
- [x] **HR 시스템**: 직원별 권한(RBAC), 근무 스케줄 설정 및 연차/휴가 결재 시스템
- [x] **정기 결제**: 토스페이먼츠 빌링키 기반 요금제 자동 결제 인프라

### 📱 B2C 보호자 플랫폼 (Mobile App & PWA)
- [x] **실시간 예약**: 샵 스케줄과 연동된 실시간 예약 신청, 수정 및 취소
- [x] **추억 앨범**: Supabase Storage 연동 미용 전/후 사진 갤러리 제공
- [x] **전자 동의서**: 법적 유효성을 갖춘 타이핑 서명 방식의 미용/케어 동의서 작성
- [x] **실시간 소통**: 샵 직원과의 1:1 채팅 및 예약 상태 변경 푸시 알림
- [x] **PWA 지원**: 앱 설치 없이 웹 링크만으로 즉시 이용 가능한 환경 구축

### ⚙️ Backend & Infrastructure
- [x] **Multi-tenancy**: RLS 기반의 완벽한 샵별 데이터 격리 및 보안
- [x] **Real-time Engine**: Supabase Realtime을 활용한 메시징 및 알림 브로드캐스팅
- [x] **Automation**: Cron Jobs를 활용한 정기 결제 처리 및 재방문 리마인더 발송

---

## 🗺️ Visionary Roadmap (로드맵)

Hugroomer는 '관리 도구'를 넘어 펫케어 생태계를 연결하는 '플랫폼'을 지향합니다.

### Phase 1: 진입장벽 제거 및 PWA 고도화
- 보호자 전용 웹(PWA) 전환 완료를 통해 앱 설치 허들 제거 및 유입률 극대화
- 미용 완료 후 "사진 확인 링크" SMS 발송 자동화를 통한 자연스러운 보호자 가입 유도

### Phase 2: 결제 인프라 기반의 단골 Lock-in
- **예약금 시스템**: 노쇼 방지를 위한 선결제 및 취소 정책 자동화 로직 도입
- **구독권/횟수권**: 정기 방문을 유도하는 월정액 구독 모델 및 횟수 기반 차감 시스템 구현

### Phase 3: 데이터 기반 플랫폼 확장
- **지도 기반 샵 검색**: 공공데이터 연동 및 미등록 샵 대상의 유저 주도 초대 시스템
- **신뢰 리뷰**: 예약 완료 건에 한정된 사진 리뷰 및 평점 시스템을 통한 샵 신뢰도 구축

---

## 🔍 Core Engineering Highlights

### 1. 고밀도 예약 시각화 알고리즘 (Greedy Column Assignment)
**Challenge:** 여러 직원의 예약이 동일 시간대에 겹칠 때, UI가 중첩되지 않으면서도 가독성을 유지해야 했습니다.  
**Solution:** 겹치는 예약 그룹을 식별하고, 각 예약에 동적 열(Column) 인덱스를 부여하는 알고리즘을 구현했습니다. 이를 통해 예약 블록의 `width`와 `left` 값을 런타임에 계산하여 겹침 정도에 따라 유연하게 배치되도록 설계했습니다.

### 2. 멀티 테넌트 보안 아키텍처 (Row Level Security)
**Challenge:** B2B SaaS로서 매장 간 데이터가 섞이는 것은 치명적인 결함입니다.  
**Solution:** 애플리케이션 레벨의 필터링에 의존하지 않고, DB 레벨에서 **Supabase RLS** 정책을 적용했습니다. 모든 쿼리에 `auth.uid()`와 `staff.shop_id`를 검증하는 정책을 심어, 개발자의 실수로 인한 데이터 유출 가능성을 원천 차단했습니다.

### 3. AI 기반 비즈니스 자동화 (Claude 3.5 Sonnet Integration)
**Challenge:** 원장님들이 직접 마케팅 메시지나 돌봄 리포트를 작성하는 데 드는 공수를 줄여야 했습니다.  
**Solution:** Anthropic의 Claude API를 연동하여, 축적된 미용 데이터를 바탕으로 "친근한", "정중한", "간단한" 세 가지 톤의 재방문 메시지 초안을 자동 생성합니다. 또한 케어 일지를 요약하여 보호자에게 감동을 주는 리포트 자동화 기능을 구현했습니다.

### 4. 무지개다리 정책 (Data Empathy Design)
**Challenge:** 반려동물이 사망하거나 샵을 옮겨 데이터를 삭제할 때 발생하는 데이터 손실 문제.  
**Solution:** 단순 삭제가 아닌 `is_deleted` 기반의 **Soft Delete**와 **Grooming History Snapshot** 전략을 도입했습니다. 반려동물 정보가 삭제되더라도 보호자에게는 과거의 미용 사진과 추억을 제공하며, 샵의 매출 장부에는 당시의 기록이 그대로 보존되도록 설계하여 비즈니스 일관성과 사용자 감동을 동시에 잡았습니다.

### 5. 한글 IME 및 포커스 트랩 최적화
**Challenge:** Radix UI Dialog 사용 시 한글 조합 중 포커스가 소실되는 고질적인 UX 이슈 해결.  
**Solution:** `onFocusOutside` 이벤트를 인터셉트하고 IME 상태를 체크하는 커스텀 핸들러를 개발하여, 한국 사용자에게 최적화된 입력 경험을 제공합니다.

---

## 🎨 UI/UX Design System & Product Thinking

1인 개발자로서 디자인과 개발의 간극을 줄이고, 일관된 브랜드 경험을 제공하기 위해 시스템 중심의 디자인 접근 방식을 채택했습니다.

### 1. Atomic Design 기반의 공통 UI 패키지
- **Shared Design System**: `packages/ui`를 통해 Web, Mobile, Landing 페이지에서 동일한 디자인 언어(색상, 타이포그래피, 컴포넌트)를 공유하도록 설계했습니다.
- **Customizing shadcn/ui**: 표준화된 라이브러리를 기반으로 Hugroomer만의 따뜻하고 신뢰감 있는 톤앤매너(Primary: Purple/Indigo)를 투영한 커스텀 테마를 구축했습니다.

### 2. 사용자 중심의 이원화된 UX 설계
- **B2B (미용샵 원장님)**: 고밀도 정보 처리가 필요한 대시보드 특성에 맞춰 **시각적 위계(Visual Hierarchy)**를 최적화했습니다. 예약 현황을 한눈에 파악할 수 있는 Gantt 차트와 빠른 액션 패널을 배치하여 운영 효율을 극대화했습니다.
- **B2C (보호자)**: 복잡한 과정을 생략한 **모바일 퍼스트 UX**를 지향합니다. 예약부터 전자 동의서 작성까지의 흐름을 선형화하여, IT 기기에 익숙하지 않은 연령층도 이탈 없이 과업을 완수할 수 있도록 설계했습니다.

### 3. 디테일한 인터랙션 고찰
- **Empty States & Loading**: 데이터가 없는 화면에서도 사용자에게 다음 행동을 가이드하는 일러스트와 문구를 배치했습니다.
- **Micro-interactions**: 예약 상태 변경 시의 즉각적인 피드백, 겹침 예약 발생 시의 시각적 경고 등 사용자 실수를 방지하는 세밀한 인터랙션을 구현했습니다.
- **Accessibility**: 다양한 환경의 원장님들을 고려하여 폰트 가독성과 대비비를 조정하고, 한글 입력 시의 포커스 이슈 등 한국적 사용 환경을 세밀하게 반영했습니다.

---

## 🚀 Project Management & Productivity (1인 개발 전략)

혼자서 기획부터 배포까지 관리하기 위해 체계적인 **Agile Work-flow**와 **Self-Documentation** 전략을 수립했습니다.

### 1. Semantic Commit & CI/CD Control
- **Conventional Commits**: `feat:`, `fix:`, `refactor:`, `chore:` 등 표준화된 커밋 메시지를 사용하여 변경 이력을 추적 가능하게 관리했습니다.
- **CI/CD Optimization**: 불필요한 빌드 리소스를 낭비하지 않기 위해 커밋 메시지에 `[skip ci]` 태그를 활용, 배포 준비가 완료된 시점에만 수동으로 배포를 트리거하는 비용 효율적인 전략을 사용했습니다.

### 2. Living Documentation
- **CLAUDE.md**: 프로젝트의 핵심 비즈니스 로직, 기술적 결정 사항, 트러블슈팅 가이드를 '단일 진실 공급원(Single Source of Truth)'으로 관리하여 개발 생산성을 높였습니다.
- **PROGRESS.md**: Phase 기반의 로드맵과 현재 진행률을 실시간으로 업데이트하여, 전체 흐름을 놓치지 않고 점진적인 기능 확장을 달성했습니다.

### 3. Issue & Risk Management
- **Phase-based Roadmap**: 전체 프로젝트를 5단계(Phase 0~5)로 세분화하여 우선순위에 따른 기능을 구현했습니다.
- **Defense Design**: 1인 운영 시 발생할 수 있는 데이터 결함을 방지하기 위해 DB 제약 조건(Constraints)과 RLS를 최우선으로 설계한 후 프론트엔드 개발에 착수했습니다.

---

## � Development History & Evolution

Hugroomer는 단순한 기능 구현을 넘어, 실제 운영 환경에서의 확장성과 유지보수성을 확보하기 위해 점진적인 아키텍처 개선을 거쳤습니다.

| 버전 | 주요 마일스톤 | 기술적 고찰 및 해결 방안 |
| :--- | :--- | :--- |
| **v0.1.0** | **Monorepo Foundation** | Web(Next.js)과 Mobile(Expo) 간의 코드 중복을 최소화하기 위해 Turborepo 기반 모노레포를 구축함. |
| **v0.5.0** | **Scheduling Engine** | 1인샵 원장의 편의성을 위해 Gantt 차트 기반 타임라인을 구현함. SSR 환경에서의 **KST/UTC 시간대 일관성** 문제를 `mounted` 훅과 전용 시간 유틸리티로 해결함. |
| **v0.8.0** | **AI & Multi-care Logic** | 기존 개별 테이블(hotel_*)의 데이터 산재 문제를 해결하기 위해 **통합 케어 테이블(`care_*`)**로 마이그레이션함. Claude API를 연동하여 반복적인 문서 작성 업무를 자동화함. |
| **v0.9.5** | **Real-time & Security** | Supabase Realtime을 도입하여 별도의 소켓 서버 없이 실시간 채팅을 구현함. 비즈니스 로직 전반에 **RLS(Row Level Security)**를 적용하여 테넌트 간 보안을 강화함. |
| **v1.0.0** | **Build Optimization** | Vercel 및 EAS(Expo Application Services) 빌드 파이프라인을 구축함. **Android New Architecture**를 활성화하여 모바일 앱의 런타임 성능을 극대화함. |

### 💡 주요 설계 고찰 (Design Decisions)

1.  **왜 Supabase인가?**
    *   1인 개발 환경에서 인증, 실시간 통신, 스토리지 인프라 구축 비용을 최소화하고 비즈니스 로직 개발에 집중하기 위해 선택했습니다. 특히 PostgreSQL의 강력한 RLS 기능을 통해 보안 로직을 DB 레벨로 이관했습니다.

2.  **Server Actions vs API Routes**
    *   Next.js 14의 Server Actions를 적극 활용하여 클라이언트-서버 간의 타입 세이프티를 강화하고, API 엔드포인트 관리 공수를 줄였습니다. 복잡한 유효성 검사는 Zod와 결합하여 처리했습니다.

3.  **Cross-Platform UI Strategy**
    *   Web 대시보드는 생산성을 위해 `shadcn/ui`를, Mobile은 네이티브 성능을 위해 `React Native`를 사용하되, `packages/ui`에서 디자인 시스템의 핵심 로직과 테마를 공유하여 브랜드 아이덴티티를 유지했습니다.

---

## 🏗 시스템 아키텍처 및 DB 설계

Hugroomer는 확장성과 유지보수성을 고려하여 관계형 데이터베이스를 설계했습니다.

- **shops**: 테넌트 마스터 정보 및 요금제 관리
- **reservations**: 비즈니스 핵심 트랜잭션 및 타임라인 연동
- **care_logs**: Claude AI 연동을 통한 자동 리포트 생성 기반 데이터
- **chat_rooms**: Supabase Realtime 기반의 실시간 소통 인프라
- **Soft Delete**: 반려동물 삭제 시 `is_deleted` 처리로 과거 기록(추억 앨범) 보존 정책 적용

*※ 상세 DB ERD 및 API 명세서는 내부 문서로 관리 중이며, 요청 시 별도 제공 가능합니다.*

---

## 🛡️ 소스코드 보호 및 이용 안내 (Source Code Policy)

### 1. 상세 소스코드 비공개 (Private Repository)
본 저장소의 상세 구현 소스코드(Server Actions, 컴포넌트 내부 로직, API 연동부 등)는 **지식재산권 보호 및 보안상의 이유로 비공개(Private)**로 관리되고 있습니다. 본 `README_PUBLIC.md`는 개발자의 아키텍처 설계 역량과 기술적 문제 해결 방안을 보여주기 위한 요약 문서입니다.

### 2. 저작권 보호
본 프로젝트의 기획, UI/UX 디자인, 고유 알고리즘, 데이터베이스 스키마 설계 및 비즈니스 모델 아이디어는 개발자 개인의 창작물입니다. **무단 전재, 복제, 상업적 이용 및 재배포를 엄격히 금지합니다.**

### 3. 기술 문의
아키텍처 설계나 특정 기술 구현 방식에 대한 상세한 논의가 필요하신 경우, 아래 연락처를 통해 문의해 주시기 바랍니다.

---

## 📬 Contact & Portfolio

- **Email**: yoonani2720@naver.com
- **LinkedIn**: https://www.linkedin.com/in/hayunan/
- **GitHub**: https://github.com/HAYUNAN

<p align="center">© 2026 Hugroomer. All rights reserved.</p>
