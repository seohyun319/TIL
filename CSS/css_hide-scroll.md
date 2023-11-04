## 특정 영역에서만 스크롤 적용 && 스크롤 숨기기

- 높이값 적용 필수

```css
overflow-y: scroll;
height: calc(100vh - 72px);

/* Chrome, Safari and Opera */
&::-webkit-scrollbar {
  display: none;
}
-ms-overflow-style: none; /* IE and Edge */
scrollbar-width: none; /* Firefox */
```

