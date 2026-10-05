# 🏢 Canias ERP Architecture & TROIA Development Handbook

## 💡 배경 및 계기 (Background)

ELT 데이터 파이프라인을 구축하며, 원천 데이터가 발생하는 ERP 모듈의 비즈니스 로직과 TROIA 개발 프레임워크에 대한 깊은 이해 부족을 절감했습니다.

단순히 DB 테이블에서 데이터를 추출하는 수준을 넘어, **화면(UI) - 이벤트(Lifecycle) - 데이터베이스(DB)**가 어떻게 유기적으로 연결되고 데이터가 변환되는지 직접 개발하고 기록하여 주도적인 데이터 엔지니어로 성장하고자 합니다.

---

## 🗺️ 현실적인 학습 및 문서화 로드맵 (Roadmap)

거대한 비즈니스 모듈(SD, MM 등)을 이론적으로 나열하기보다, **실제 TROIA 화면 개발과 데이터 흐름을 이해하는 실전 위주**로 단계별 정리합니다.

```text
1. Framework & Lifecycle (기초 및 화면 생명주기)
   ↓
2. TROIA Scripting & Commands (자주 쓰는 필수 명령어 / 함수)
   ↓
3. Custom Development & Data Binding (실전 화면 개발 및 DB 연동)
   ↓
4. Business Domains (향후 업무 필요 시 도메인 확장)
