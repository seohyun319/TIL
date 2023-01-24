## Request path contains unescaped characters 에러

```
client  | TypeError [ERR_UNESCAPED_CHARACTERS]: Request path contains unescaped characters
```

### 에러 원인

- request url에 치환되지 않은 문자가 들어옴
- 이전까지는 변환 안 해도 멀쩡하게 잘 돌아갔는데 ssr로 바꾸니까 발생

### 해결 방법

한글이 들어간 부분을 `encodeURI`로 감싸준다!

```js
axios.get('/spellings?text="' + encodeURI(searchText) + '"');
```
