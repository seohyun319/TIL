> Error Code: 1364. Field doesn't have a default values

### 에러 원인

테이블 생성 시 default 값을 지정해주지 않음

### 2가지 해결법

1. 일시 해제: `SET session sql_mode = 'NO_ENGINE_SUBSTITUTION';`
2. my.cnf 에서 기본 설정된 STRICT 모드 해제
   #sql_mode=NO_ENGINE_SUBSTITUTION,STRICT_TRANS_TABLES
   sql_mode=NO_ENGINE_SUBSTITUTION
