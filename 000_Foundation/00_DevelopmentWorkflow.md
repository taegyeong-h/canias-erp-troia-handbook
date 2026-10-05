## caniasERP 환경에서 신규 신규 모듈/화면을 개발할 때 준수하는 개발 단계별 트랜잭션(Transaction) 및 작업 순서입니다.

1. 개발 환경 설정 및 핫라인 연결
트랜잭션: DEVT06 (Hotline Management)

작업 내용:

개발 서버 접속 및 핫라인(Hotline) 환경 구성

세션 연결 상태 점검 및 작업 대상 개발 버전/시스템 영역 지정

2. 데이터 구조 설계 및 DB 테이블 생성
트랜잭션: DEVT02 (Data Dictionary) / DEVT01 (Table Definition)

작업 내용:

DEVT02: 신규 필드에 사용할 도메인 및 데이터 엘리먼트 정의

DEVT01: 데이터베이스 테이블(DB Table) 생성, PK 및 인덱스(Index) 설정, 실제 DB 반영(Check Table)

3. 트랜잭션 및 화면(UI) 개발
트랜잭션: DEVT03 (Dialog / Transaction Development)

작업 내용:

신규 트랜잭션 코드 생성

화면 레이아웃(Dialog UI) 설계 및 컨트롤(Grid, Edit box, Button 등) 배치

각 이벤트(BEFORE, AFTER, CLICK 등)에 TROIA 스크립트 작성

4. 공통 모듈 및 글로벌 메서드 구현 (선택)
트랜잭션: DEVT05 (Global Methods & Classes)

작업 내용:

여러 화면에서 재사용할 비즈니스 로직 및 공통 함수 구현

외부 시스템 연동 및 복잡한 연산 로직 모듈화

5. 소스 이관 및 운영 반영
트랜잭션: DEVT07 (Transport Management)

작업 내용:

개발 완료 객체(Table, Dialog, Method 등) 락(Lock) 해제 및 이관 요청 생성

QA(검증) 및 PROD(운영) 서버로 핫라인 변경 사항 इ관(Transport)
