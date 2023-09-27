## yarn start로 개발 중 메모리 부족으로 꺼질 때

node에 할당된 램 용량 확인하기

```bash
node -e 'console.log(v8.getHeapStatistics().heap_size_limit/(1024*1024))'
```

할당된 램보다 더 큰 용량을 할당해주기

```bash
export NODE_OPTIONS="--max-old-space-size=8192"
export NODE_OPTIONS="--max-old-space-size=4096"
```
