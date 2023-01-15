## styled-components에서 확장 스타일링

기존에 선언한 컴포넌트의 css를 그대로 활용하면서 새로 추가할 수 있는 방법

```js
const Container = styled.div`
  width: 100%;
  height: 100vh;
`;

const BlackContainer = styled(Container)`
  background-color: black;
`;

const RedContainer = styled(Container)`
  background-color: red;
`;

return (
  <>
    <BlackContainer />
    <RedContainer />
  </>
);
```
