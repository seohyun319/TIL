> code: 'ER_NOT_SUPPORTED_AUTH_MODE',
> errno: 1251,
> sqlMessage: 'Client does not support authentication protocol requested by server; consider upgrading MySQL client',
> sqlState: '08004',
> fatal: true

### 에러 원인

사용 권한 오류

### 해결법

`ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY '비밀번호';` 입력
