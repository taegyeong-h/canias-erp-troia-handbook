# CACHEALLTROIAITEMS

## 1. 개요 (Overview)
* Canias ERP의 모든 클래스(`Class`), 다이얼로그(`Dialog`), 컴포넌트(`Component`), 리포트(`Report`) 소스코드와 UI 메타데이터를 DB/서버에서 읽어와 **RAM(캐시 메모리)에 미리 로딩**하는 시스템 명령어입니다.
* 화면을 처음 열 때 발생하는 네트워크/DB 지연을 줄여 시스템 반응 속도를 높이는 목적으로 사용됩니다.

---

## 2. API 명세 (Specification)

| 구분 | 내용 |
| :--- | :--- |
| **중요도 / 빈도** | `03` (시스템 초기화·최적화용 / 일반 화면 개발 시 작성할 일 거의 없음) |
| **반환 타입 (Return)** | `void` (반환값 없음) |
| **매개변수 개수** | `0개` 또는 `1개` (가변/선택) |

---

## 3. 매개변수 상세 (Parameters)

| 순서 | 매개변수명 | 타입 | 필수 여부 | 설명 |
| :---: | :--- | :--- | :---: | :--- |
| 1 | `prefix` | `STRING` | 선택 (Optional) | 캐시에 올릴 아이템 이름의 시작 접두사 (예: `'SAL%'`) |

> **Note:** 매개변수를 전달하지 않고 `CACHEALLTROIAITEMS();` 단독 호출 시 **시스템 전체 아이템**을 메모리에 올립니다.

---

## 4. 실전 사용 예시 (Code Example)

```troia
/* 1. 시스템 전체 아이템을 메모리(캐시)에 로딩 */
CACHEALLTROIAITEMS();

/* 2. 'SAL'로 시작하는 영업(Sales) 모듈 관련 아이템만 선택 로딩 */
CACHEALLTROIAITEMS('SAL%');
