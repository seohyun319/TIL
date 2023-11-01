# window 특정 포트 사용 중인 서비스 확인하기, 끝내기

확인하기

```
netstat -ano | findstr 포트번호
```

<br />

특정 프로세스 끝내기

```
taskkill /f /pid 프로세스번호
```

### 상황
도커 켰는데 3307 포트 사용 중..! 3307 쓰고 있던 프로세스 종료 후 재실행함

---

[특정 포트 사용 프로세스 찾기](https://blueyikim.tistory.com/202)
