# next Type error: 'Component' cannot be used as a JSX component.

### 에러 로그

Type error: 'Component' cannot be used as a JSX component.
```
Type error: 'Component' cannot be used as a JSX component.
#0 22.70   Its element type 'Component<any, any, any> | ReactElement<any, any> | null' is not a valid JSX element.
#0 22.70     Type 'Component<any, any, any>' is not assignable to type 'Element | ElementClass | null'.
#0 22.70       Type 'Component<any, any, any>' is not assignable to type 'ElementClass'.
#0 22.70         The types returned by 'render()' are incompatible between these types.
#0 22.70           Type 'React.ReactNode' is not assignable to type 'import("/app/node_modules/@types/react-dom/node_modules/@types/react/ts5.0/index").ReactNode'.
#0 22.70             Type 'ReactElement<any, string | JSXElementConstructor<any>>' is not assignable to type 'ReactNode'.
#0 22.70               Property 'children' is missing in type 'ReactElement<any, string | JSXElementConstructor<any>>' but required in type 'ReactPortal'.
#0 22.70
#0 22.70   14 |   return (
#0 22.70   15 |     <QueryClientProvider client={queryClient}>
#0 22.70 > 16 |       <Component {...pageProps} />;
#0 22.70      |        ^
#0 22.70   17 |     </QueryClientProvider>
#0 22.70   18 |   );
#0 22.70   19 | }
```


### 원인

버전 18로 업그레이드되었는데 라이브러리는 17에 dependency를 둔 것 때문으로 추정됨

### 해결책

package.json에 resolutions 추가

```jsx
 // package.json
 "resolutions": {
    "@types/react": "17.0.2",
    "@types/react-dom": "17.0.2"
  },
```

### 참고

[Next.js - Component cannot be used as a JSX component](https://soft91.tistory.com/104)
