# TROIA MESSAGE 명령어 가이드

CANIAS ERP(TROIA) 개발 시 사용자에게 알림, 경고, 에러, 입력 팝업 등을 띄울 때 사용하는 `MESSAGE` 명령어의 구조와 규칙을 정리한 문서입니다.

## 1. 기본 구문 (Syntax)

```troia
MESSAGE <모듈명> <타입접두사+번호> [OPTIONS/DEFAULT] WITH <파라미터>;
>> MESSAGE SYS E100 WITH '01' DEBIA_NAME;

/*HT 00000055 tghong 06.10.2026
카테고리코드, 약어는 필수 입력
*/

IF CDFCEDU201BOOKCATEGORY_CATEGORY == '' THEN
    MESSAGE BAS E2000 WITH '카테고리코드는 필수입력입니다';
    RETURN 0;
ENDIF;
IF CDFCEDU201BOOKCATEGORY_KEYWORD == '' THEN
    MESSAGE BAS E2000 WITH '약어는 필수입력입니다';
    RETURN 0;
ENDIF;

RETURN 1;



```

<img width="1644" height="845" alt="image" src="https://github.com/user-attachments/assets/4e7fb20c-424b-4c66-892e-77545ad5b16c" />

### 메시지 코드는 `SYST03` 트랜잭션 입력 후, 메시지키 , 메시지번호로 적절한거 찾음
<img width="1734" height="780" alt="image" src="https://github.com/user-attachments/assets/21e16588-ae91-4aa8-a4cb-c9f4ad80b022" />
