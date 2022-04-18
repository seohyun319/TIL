> Error Code: 1175. You are using safe update mode and you tried to update a table without a WHERE that uses a KEY column
> To disable safe mode, toggle the option in Preferences -> SQL Editor and reconnect.

### 에러 원인

키 값만을 이용하지 않고, 좀 더 넓은 범위의 sql 적용 시. (다수의 레코드를 수정하려 함)

### 2가지 해결법

1. 일시 해제: `SET SQL_SAFE_UPDATES = 0;`
2. Preferences -> SQL Editor에서 safe mode를 disable로 바꿈
