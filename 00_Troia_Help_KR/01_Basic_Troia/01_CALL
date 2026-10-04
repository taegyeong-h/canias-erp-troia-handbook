# CALL

## 1. 개요 (Overview)
* TROIA에서 **트랜잭션(Transaction) 실행, 다이얼로그(Dialog) 창 열기, 리포트(Report) 인쇄**를 수행하는 가장 대표적인 실행 명령어입니다.
* 뒤에 오는 대상(`TRANSACTION`, `DIALOG`, `REPORT`)에 따라 동작과 지원하는 옵션이 달라집니다.

---

## 2. API 명세 (Specification)

| 구분 | 내용 |
| :--- | :--- |
| **중요도 / 빈도** | `01` (매일 사용하는 필수 핵심 구문) |
| **반환 타입 (Return)** | `void` (반환값 없음) |
| **주요 대상** | `TRANSACTION`, `DIALOG`, `REPORT` |

---

## 3. 주요 형태 및 옵션 분석

### ① DIALOG 호출 (`CALL DIALOG`)
* 특정 다이얼로그(화면/팝업)를 화면에 띄웁니다.
* `WITH LOCATION {x},{y}` 및 `SIZE {width},{height}` 옵션으로 팝업 위치와 크기를 직접 지정할 수 있습니다.

### ② TRANSACTION 호출 (`CALL TRANSACTION`)
* 다른 ERP 트랜잭션 화면이나 비즈니스 로직을 호출합니다.
* **`WITH WAIT`**: 호출한 트랜잭션이 종료될 때까지 현재 로직을 대기(동기 실행)시킵니다.
* **`INSERVER`**: 클라이언트 화면 없이 서버 백그라운드 배치(Batch)로 트랜잭션을 실행합니다.
  * 실행 중 발생한 오류 로그는 `SYSBATCHMESSAGES` 테이블에 기록됩니다.

### ③ REPORT 출력 (`CALL REPORT`)
* 작성된 출력물(리포트)을 모니터, 프린터, 파일 등으로 보냅니다.
* **`TO SCREEN`**: 화면 팝업 미리보기
* **`TO PRINTER`**: 프린터로 직접 인쇄
* **`ATCHFILE` / `ATCHDESC`**: 리포트에 특정 파일 첨부

---

## 4. 실전 사용 예시 (Code Example)

```troia
/* 1. 다이얼로그(팝업창) 열기 */
CALL DIALOG DFCEDUT202F002;

/* 2. 다이얼로그 위치 및 크기 지정하여 열기 */
CALL DIALOG DFCEDUT202F002 WITH LOCATION 100,100 SIZE 800,600;

/* 3. 파라미터를 전달하며 다른 트랜잭션 동기 호출 (완료 시까지 대기) */
CALL TRANSACTION SAL001 '1000', 'SO20261001' WITH WAIT;

/* 4. 백그라운드 서버 배치로 트랜잭션 실행 */
CALL TRANSACTION PUR001 INSERVER WITH BATCH;

/* 5. 리포트 화면 미리보기 출력 */
CALL REPORT SALR01 TO SCREEN;
