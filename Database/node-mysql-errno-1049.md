> code: 'ER_BAD_DB_ERROR',
> errno: 1049,
> sqlMessage: "Unknown database 'roomescape_review_project'",
> sqlState: '42000',
> index: 0,
> sql: 'USE roomescape_review_project';

### 해결법

```js
//mysql 연결
const con = mysql.createConnection({
  host: "localhost",
  // 포트가 일반적으로 3306인데 나는 MariaDB가 3306에 있어서 포트 설정 추가해줌
  port: "3307",
  user: "root",
  password: "PW",
});
```

MySQL cmd에 `USE roomescape_review_project` 입력해줌. (roomescape_review_project는 db로 쓰는 프로젝트명)
