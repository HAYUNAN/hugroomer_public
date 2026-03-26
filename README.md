# 🐾 Hugroomer (허그루머)

**애견미용샵 & 펫케어 비즈니스를 위한 올인원 B2B SaaS 플랫폼**

> **"원장님은 미용에만 집중하세요, 나머지는 허그루머가 관리합니다."**  
> Hugroomer는 1인샵부터 대형 프랜차이즈까지 아우르는 애견 미용 산업의 디지털 전환(DX)을 목표로 기획/개발된 플랫폼입니다. 복잡한 예약 타임라인 최적화, AI 기반 고객 관리, 그리고 멀티 테넌트 보안 아키텍처를 실무 수준으로 구현했습니다.

---

## ✨ 주요 기능 및 비즈니스 가치

| 기능 | 설명 |
|---|---|
| **스마트 타임라인** | **Greedy Column Assignment 알고리즘** 기반 Gantt 차트. 예약 충돌을 시각화하고 최적의 스케줄링을 지원합니다. |
| **AI 고객 리텐션** | **Claude 3.5 Sonnet** 연동. 방문 주기를 분석하여 개인화된 재방문 독려 메시지를 자동 생성합니다. |
| **올인원 케어 모듈** | 미용을 넘어 펫호텔, 유치원 등 부가 서비스 통합 관리 및 AI 돌봄 리포트 기능을 제공합니다. |
| **멀티 플랫폼 지원** | Next.js 기반 대시보드와 React Native(Expo) 보호자 앱을 통해 샵과 고객을 실시간으로 연결합니다. |
| **비즈니스 인프라** | 토스페이먼츠 정기 결제, 직원별 매출 통계, 전자 동의서 등 실제 운영에 필요한 모든 도구를 포함합니다. |

---

##  기술 스택

### Frontend
- **Framework**: Next.js 14 (App Router), React Native (Expo)
- **Language**: TypeScript
- **Styling**: TailwindCSS, shadcn/ui
- **State/Data**: Supabase Realtime, TanStack Query

### Backend & Infrastructure
- **Backend**: Next.js Server Actions (Serverless)
- **Database**: Supabase (PostgreSQL)
- **AI**: Anthropic Claude API (3.5 Sonnet)
- **Auth/Storage**: Supabase Auth & Storage
- **Deployment**: Vercel

### Architecture
- **Monorepo**: Turborepo를 활용한 코드 공유 및 패키지 관리 효율화
- **Security**: **Row Level Security (RLS)**를 통한 완벽한 샵별 데이터 격리(Multi-tenancy) 구현

---

## 🔍 기술적 도전 및 해결 과정 (Engineering Challenges)

### 1. SSR과 클라이언트 간의 시간대 불일치 해결
**Challenge:** 서버(UTC)와 브라우저(KST) 간의 시간 차이로 인해 SSR 시 예약 블록의 위치가 어긋나는 하이드레이션 오류가 발생했습니다.  
**Solution:** `mounted` 상태 관리를 통해 클라이언트 마운트 이후에만 KST 기준으로 레이아웃을 계산하도록 구현하고, 모든 날짜 연산을 공통 유틸리티로 캡슐화하여 일관성을 확보했습니다.

### 2. 고밀도 예약 데이터 시각화 알고리즘 최적화
**Challenge:** 동일 시간대에 여러 직원의 예약이 겹칠 경우 UI가 뭉개지는 현상이 발생했습니다.  
**Solution:** **Greedy Column Assignment** 알고리즘을 도입하여 겹치는 그룹을 식별하고 가용 너비를 동적으로 분할 배치함으로써, 정보 손실 없는 타임라인 뷰를 완성했습니다.

### 3. 멀티 테넌트 보안 아키텍처 (RLS)
**Challenge:** B2B SaaS 특성상 타 매장의 데이터 노출은 치명적인 결함입니다.  
**Solution:** DB 레벨에서 **Supabase RLS** 정책을 엄격히 적용했습니다. `auth.uid()`와 `staff` 테이블의 관계를 정의하여, 애플리케이션 로직의 실수와 상관없이 데이터가 물리적으로 격리되도록 설계했습니다.

### 4. 한글 IME 입력 유저 경험(UX) 개선
**Challenge:** Radix UI Dialog 내에서 한글 입력 시 조합 중 포커스가 소실되는 브라우저 특유의 이슈를 발견했습니다.  
**Solution:** `onFocusOutside` 이벤트를 인터셉트하여 IME 입력 중 포커스 이탈을 방지하는 핸들러를 구현하여 입력 경험을 최적화했습니다.

---

## 🏗 시스템 아키텍처 및 DB 설계

Hugroomer는 확장성과 유지보수성을 고려하여 관계형 데이터베이스를 설계했습니다.

- **shops**: 테넌트 마스터 정보 및 요금제 관리
- **reservations**: 비즈니스 핵심 트랜잭션 및 타임라인 연동
- **care_logs**: Claude AI 연동을 통한 자동 리포트 생성 기반 데이터
- **chat_rooms**: Supabase Realtime 기반의 실시간 소통 인프라
- **Soft Delete**: 반려동물 삭제 시 `is_deleted` 처리로 과거 기록(추억 앨범) 보존 정책 적용

---

## 🗺 프로젝트 로드맵

- **Phase 1**: 예약·고객·서비스 관리 핵심 기능 구축 (완료)
- **Phase 2**: 미용 기록 사진 자동화 및 AI 재방문 문자 시스템 (완료)
- **Phase 3**: 보호자 전용 모바일 앱 및 전자 동의서 시스템 (완료)
- **Phase 4**: 토스페이먼츠 기반 정기 결제 및 예약금 인프라 (진행 중)
- **Phase 5**: 보호자 PWA 전환 및 샵 탐색 지도 서비스 (예정)

---

## 🛡️ 저작권 및 이용 안내 (Disclaimer)

### 1. 저작권 보호
본 프로젝트는 개발자의 개인 포트폴리오 용도로 제작되었습니다. 본 저장소의 모든 소스 코드, 기획 문서, 비즈니스 로직 및 디자인 자산에 대한 **무단 전재, 복제, 상업적 이용 및 재배포를 엄격히 금지합니다.** 

### 2. 기술적 참고 사항
본 프로젝트에 포함된 브랜드명(Hugroomer) 및 고유의 비즈니스 모델 아이디어는 보호받고 있습니다. 개인적인 학습 목적의 코드 참고 외에, 본 서비스를 모방한 상업적 서비스 출시는 법적 책임을 물을 수 있습니다.

### 3. 보안 고지
실제 운영 환경에 필요한 API Key 및 보안 토큰은 환경 변수로 격리되어 관리되고 있으며, 본 저장소에는 포함되어 있지 않습니다.

---

## 📬 Contact

프로젝트에 대한 자세한 설명이나 협업 제안은 아래 채널로 문의 부탁드립니다.

- **Email**: yoonani2720@naver.com
- **LinkedIn**: https://www.linkedin.com/in/hayunan/

>© 2026 Hugroomer. All rights reserved.
