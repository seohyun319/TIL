> Expression expected.ts(1109)

### 해결
리턴값이 있어야 한다! 

기존 코드
```js
const selectDetailInfo = () => {
  detailInfo?.type === "spacing" ? scrapSpacing(id) : scrapSpelling(id);
};
```

바꾼 코드
```js
const selectDetailInfo = () => {
  if (detailInfo?.type === "spacing") {
    return scrapSpacing(id);
  } else {
    return scrapSpelling(id);
  }
};
```
