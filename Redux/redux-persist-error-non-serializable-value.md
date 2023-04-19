> A non-serializable value was detected in an action, in the path: `register`.

```
Value: ƒ register(key) {
    _pStore.dispatch({
      type: _constants__WEBPACK_IMPORTED_MODULE_0__.REGISTER,
      key: key
    });
}
```

> Take a look at the logic that dispatched this action: {
> type: 'persist/PERSIST',
> register: ƒ register(key),
> rehydrate: ƒ rehydrate(key, payload, err)
> }
>
> (See https://redux.js.org/faq/actions#why-should-type-be-a-string-or-at-least-serializable-why-should-my-action-types-be-constants)
>
> (To allow non-serializable values see: https://redux-toolkit.js.org/usage/usage-guide#working-with-non-serializable-data)

### 해결 방법

middleware 추가해서 해결! thunk middleware 없이 redux persist를 쓰면 나는 에러라고 한다.

```js
export const store = configureStore({
  reducer: persistedReducer,
  middleware: (getDefaultMiddleware) =>
    getDefaultMiddleware({
      serializableCheck: {
        ignoredActions: [FLUSH, REHYDRATE, PAUSE, PERSIST, PURGE, REGISTER],
      },
    }),
});
```
