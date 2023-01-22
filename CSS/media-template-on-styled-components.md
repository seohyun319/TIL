## styled components에서 media 쿼리 세팅

```js
const customMediaQuery = (maxWidth: number): string => {
  return `@media (max-width: ${maxWidth}px)`;
};

const media = {
  custom: customMediaQuery,
  desktop: customMediaQuery(922),
  tablet: customMediaQuery(768),
  phone: customMediaQuery(576),
};
```

사용

```js
const Content = styled.div`
  height: 3em;
  width: 3em;
  background: gray;

  ${media.desktop} {
    background: red;
  }
  ${media.tablet} {
    background: blue;
  }
  ${media.phone} {
    background: green;
  }
`;
```

[참고](https://velog.io/@hwang-eunji/styled-component-typescript)
