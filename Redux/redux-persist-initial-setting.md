## redux toolkit에 redux persist 얹기

src/\_app/store.ts

```js
import { configureStore } from "@reduxjs/toolkit";
import { combineReducers } from "redux";
import {
  persistStore,
  persistReducer,
  FLUSH,
  REHYDRATE,
  PAUSE,
  PERSIST,
  PURGE,
  REGISTER,
} from "redux-persist";
import storage from "redux-persist/lib/storage"; // 로컬 저장소
// import storageSession from "redux-persist/lib/storage/session"; // 세션 저장소에 저장
import qnaReducer from "../_reducer/qnaReducer";
import testReducer from "../_reducer/testReducer";
import userReducer from "../_reducer/userReducer";

// 리듀서가 여러 개면 합치기
const reducers = combineReducers({
  test: testReducer,
  user: userReducer,
  qna: qnaReducer,
});

// 새 persist 선언
const persistConfig = {
  key: "root", // reducer의 데이터 저장 시작 지점
  version: 1,
  storage, // storage면 local storage,
  //storage: storageSession이면 session storage
  // whitelist: ["user"], // 사용할 리듀서
  // blacklist: [] //사용하지 않을 리듀서
};

// persistConfig와 reducers가 합쳐진 persistReducer
const persistedReducer = persistReducer(persistConfig, reducers);

export const store = configureStore({
  reducer: persistedReducer,
  // thunk middleware 없이 redux persist를 쓰기 위한 세팅
  middleware: (getDefaultMiddleware) =>
    getDefaultMiddleware({
      serializableCheck: {
        ignoredActions: [FLUSH, REHYDRATE, PAUSE, PERSIST, PURGE, REGISTER],
      },
    }),
});

// 기존 store에 persist store 세팅
export const persistor = persistStore(store);

// -----리덕스 툴킷 세팅
// Infer the `RootState` and `AppDispatch` types from the store itself
export type RootState = ReturnType<typeof store.getState>;
// Inferred type: {posts: PostsState, comments: CommentsState, users: UsersState}
export type AppDispatch = typeof store.dispatch;
```

pages/\_app.tsx

```js
import type { AppProps } from "next/app";
import { persistor, store } from "../src/_app/store";
import { Provider } from "react-redux";
import { PersistGate } from "redux-persist/integration/react";

function MyApp({ Component, pageProps }: AppProps) {
  return (
    <Provider store={store}>
      {/* PersistGate로 컴포넌트 매핑*/}
      <PersistGate loading={null} persistor={persistor}>
        <Component {...pageProps} />
      </PersistGate>
    </Provider>
  );
}

export default MyApp;
```

참고: [RTK 공식문서](https://redux-toolkit.js.org/usage/usage-guide)
