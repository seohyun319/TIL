### 문제 상황

> redux-persist: config.storage is required. Try using one of the provided storage engines `import storage from 'redux-persist/lib/storage'`

redux-persist를 localStorage가 아니라 sessionStorage에 저장되게 세팅하려고 했더니 storageSession을 못 읽음.

### 해결 방법

`storageSession,` 형태가 아니라 `storage: storageSession,` 형태로 세팅!
키값이 storageSession으로 돼서 storage가 없다고 판단했던 것.

```js
const persistConfig = {
  key: "root",
  //기존
  // storageSession,
  storage: storageSession, // session에 저장
};
```

참고 https://github.com/rt2zz/redux-persist/issues/658
